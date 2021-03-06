# Pairing Process

Once the sender discovers the AirPlay server, it can get access to he AirPlay service. No matter what function the sender wants to consume, it must establish a connection session to the AirPlay service. To establish the connection session, AirPlay server and sender need to verify each other. This is so called pairing process. The diagram below illustrates the interaction between sender and server during the pairing process.

<center>
<a href="images/pairing-interaction.png"><img src="images/pairing-interaction.png" alt></a>
<br/>
<em>Pairing Process Interaction Flow</em>
</center>

1. The sender delivers **GET /info RTSP** request to the server
    
    **Request:**
    ```
    GET /info RTSP/1.0
    Active-Remote: 354444643
    CSeq: 0
    Content-Length: 70
    Content-Type: application/x-apple-binary-plist
    DACP-ID: 7136391BB370A579
    User-Agent: AirPlay/425.1
    X-Apple-ProtocolVersion: 1
    
    bplist00...Yqualifier..ZtxtAirPlay..................................."
    ```
    You may note that this is a request with GET method, but it has body data. Because it is not HTTP but RTSP protocol data.
    
    For this request, we can ignore the body data and response with a binary property list data including required information. For example, reply his  request with the following response.

    **Response:**
    ```
    Audio-Jack-Status: Connected; type=digital
    CSeq: 0
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 952
    Content-Type: application/x-apple-binary-plist
    
    bplist00.......	........"-.............#.XdeviceID\AABBCCDDEEFFXfeatures.R..._..keepAliveLowPower..   _..keepAliveSendStatsAsBody..ZmacAddress_.    AA:BB:CC:DD:EE:FFUmodelZAppleTV3,2Tname_..APS[AA:BB:CC:DD:EE:FF]]   sourceVersionV220.68[statusFlags.DRpi_.    b08f5a79-db29-4384-b456-a4784d9e6055RpkO.   @99FD4299889422515FBD27949E4E1E21B2AF50A454499E3D4BE75A4E0F55FE63Rvv.   .\audioFormats..... ..!Ttype. _..audioInputFormats....._..   audioOutputFormats.....^audioLatencies.$.%')+&(*,Ttype.   `YaudioTypeWdefault_..inputLatencyMicros........._..    utputLatencyMicros.........Xdisplays./.02468:<>@BD13579;=?   ACEXfeatures..Vheight..8\heightPixels..8^heightPhysical.........   Uwidth... widthPixels...]widthPhysical.........[refreshRate#......N@   [overscanned.Xrotation.Tuuid_.$e5f7a68d-7b0f-4305-984b-974f677a150b..   .).2.?.H.M.. c.~.............................a.d.f.s.u.|.............   ....................&./.1.H.Q.S.Z.].j.m.|............................   ..............F. ...............
    ```

    The binary property list data in the response body above can be built as follows:
    ```cpp
    auto_plist info = plist_object_dict(15,
        "deviceID", plist_object_string(config_->deviceID().c_str()),
        "features", plist_object_integer(config_->features()),
        "keepAliveLowPower", plist_object_integer(1), 
        "keepAliveSendStatsAsBody", plist_object_integer(1), 
        "macAddress", plist_object_string(config_->macAddress().c_str()), 
        "model", plist_object_string(config_->model().c_str()), 
        "name", plist_object_string(config_->name().c_str()), 
        "sourceVersion", plist_object_string(config_->serverVersion().c_str()), 
        "statusFlags", plist_object_integer(config_->statusFlag()), 
        "pi", plist_object_string(config_->pi().c_str()), 
        "pk", plist_object_data((uint8_t *)config_->pk().c_str(), (uint32_t)config_->pk().length()),
        "vv", plist_object_integer(config_->vv()), 
        "audioFormats",
        plist_object_array(1,
            plist_object_dict(3, 
                "type", plist_object_integer(96), 
                "audioInputFormats", plist_object_integer(0x01000000),
                "audioOutputFormats", plist_object_integer(0x01000000))),
        "audioLatencies", plist_object_array(1,
            plist_object_dict(4, 
                "type", plist_object_integer(96), 
                "audioType", plist_object_string("default"),
                "inputLatencyMicros", plist_object_integer(0),
                "outputLatencyMicros", plist_object_integer(0)
            )
        ),
        "displays", plist_object_array(1,
            plist_object_dict(11,
                "features", plist_object_integer(14),
                "height", plist_object_integer(config_->display().height()), 
                "heightPixels", plist_object_integer(config_->display().height()),
                "heightPhysical", plist_object_integer(0), 
                "width", plist_object_integer(config_->display().width()), 
                "widthPixels", plist_object_integer(config_->display().width()), 
                "widthPhysical", plist_object_integer(0), 
                "refreshRate", plist_object_real(config_->display().refreshRate()),
                "overscanned", plist_object_true(), 
                "rotation", plist_object_true(), 
                "uuid", plist_object_string(config_->display().uuid().c_str())
            )
        )
    );
    ```
    
    You need to be careful with the response data, because this will impact the following behavior of the sender. If you choose to response with a very high server version, maybe you cannot handle the subsequent requests due to the latest encryption algorithm.
    
    This is the first request and response sample in this document, and there are some important and common rules to be noted:

    - *The response must include **Date** item*
    - *The response must include **Session** item with whatever hex value you want, but do not change it during one session*
    - *If the request contains **CSeq**, then the response must include the same **CSeq** and value*
    - *Include **Audio-Jack-Status: Connected; type=digital** for all responses except RECORD and SET_PARAMETER requests*
    
2. The sender delivers **POST /fp-setup RTSP** request to the server

    **Request:**
    ```
    POST /fp-setup RTSP/1.0
    X-Apple-ET: 32
    Content-Length: 16
    Content-Type: application/octet-stream
    CSeq: 1
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1   
    FPLY............
    ```

    The second request from sender starts the real fairplay pairing process. In this request body it is a FPLY message. All FPLY messages has the common structure:
    ```cpp
    // 0      7 8     15 16    23 24    31  
    // +--------+--------+--------+--------+ 
    // |   F    |    P   |   L    |    Y   | 
    // +--------+--------+--------+--------+ 
    // |MajorVer|MinorVer| Phase  |  data  |
    // +--------+--------+--------+--------+ 
    // |         ... data ...              |
    // +-----------------------------------+
    // |              ...                  |
    // +-----------------------------------+

        PACKED(struct fp_header_s {
            uint8_t signature[4]; // Always 'FPLY'
            uint8_t major_version;
            uint8_t minor_version;
            uint8_t phase;
        });
        typedef fp_header_s fp_header_t;
    ```

    When the server receives the fp-setup request it needs to verify the signature FPLY first. Then it needs to verify the major version, currently we process this request only if major version is 3. Next the server needs to check the phase value to perform valid operation.

    The *phase* field in this request is 0x01, it indicates the sender is query the fairplay mode key for current session. The *mode* value is in the request body with byte offset 14, that is req.body[14]. In response to this request, the server needs to send a public key or something similar to the sender according to the mode. The response content is 142 bytes.

    **Response:**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 1
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 142
    Content-Type: application/octet-stream
    
    FPLY............?..%!..1*.....#+cv...p."...'7.......-...I...e...{...f=!...e.>......	Z.|=.%I	..1..9..44..B.:........mJt;F.   .d.D..U...U..I.......
    ```
    
3. The sender delivers **POST /fp-setup RTSP** request to the server
    
    **Request:**
    ```
    POST /fp-setup RTSP/1.0
    X-Apple-ET: 32
    Content-Length: 164
    Content-Type: application/octet-stream
    CSeq: 2
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1
    
    FPLY.............qyn......s.].3}.PS.........v..a&&...Eb..K.k+V.....I..........;.I..omR...._Q.~.k<....nz6.   ' 2.....I..f{.W.	.........e.y.2.dFR....xR4s..r.N..'...d.dB.
    ```

    The *phase* field in this request is 0x03, it indicates this request contains the fairplay key message. The key message is 164 bytes. The sever needs to keep this key message and in the following interaction this key message will be used to decoding the client AES key.

    For this request, the server needs to reply a 32 bytes message to the sender. The first 12 bytes is fixed value we called fairplay header, and the remaining 20 bytes is just taken from the request body from offset 144 with length 20, that is req.body[144:20].

    **Response:**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 2
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 32
    Content-Type: application/octet-stream
    
    FPLY........xR4s..r.N..'...d.dB.
    ```