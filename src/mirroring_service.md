# Mirroring Service

After the pairing process has been finished successfully, the sender can start request the screen mirroring service. The diagram below describes the interaction flow of starting screen mirroring.

<center>
<a href="images/mirroring-service.png"><img src="images/mirroring-service.png" alt></a>
<br/>
<em>Mirroring Service Interaction Flow</em>
</center>

We will not talk about pairing process again, please refer to the previous content.

1. The sender delivers **SETUP rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    SETUP rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 535
    Content-Type: application/x-apple-binary-plist
    CSeq: 3
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1   
    bplist00...........	
    ..
    .................RetSeiv^timingProtocol[sessionUUIDVosName^osBuildVersion]sourceVersionZtimingPort_.   isScreenMirroringSessionYosVersionTekeyXdeviceIDUmodelTnameZmacAddress. O..0......FTRM.H.R^SNTP_   $48FE92D4-3786-4D24-8270-752ACCCF8A47XMac OS XV19H524U425.1...	W10.15.7O.HFPLY.......<....%V.&..&k....}..........n.t...   A.Z.8......f....Q....]iuh._..88:66:5A:15:D7:E1^MacBookPro16,1_..SHEENTIAN-MBP00_..88:66:5A:15:D7:E1...).,.0.?.K.R.a.o.z...   .............................%.p......................................
    ```

    This request contains a binary plist data in the body and the plist consist of the following structure:
    ```json
    {
        deviceID = "4C:57:CA:46:07:FC";
        diagnosticsAndUsage = 1;
        eiv = <5e830184 fea012b8 3bbd456d b761f798>;  // AES initial vector
        ekey = <data>;                                // AES key
        et = 32;
        internalBuild = 1;
        isScreenMirroringSession = 1;
        macAddress = "4C:57:CA:46:07:FA";
        model = "iPhone8,4";
        name = "hr\U7684 iPhone";
        osBuildVersion = 16B92;
        osName = "iPhone OS";
        osVersion = "12.1";
        sessionUUID = "42CD0A19-2E4B-4355-BED6-575FA83A60DA";
        sourceVersion = "373.9.1";
        timingPort = 63254;                         // NTP server port in the sender
        timingProtocol = NTP;
    }
    ```

    The sever needs to store the *eiv* and *ekey* for initializing the AES crypto module, and then launches a time syncing client with the sender IP and *timingPort*. The time syncing client is actually a TCP client. The detailed implementation of the time syncing client will be discussed in the following sections.

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 3
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 83
    Content-Type: application/x-apple-binary-plist
    
    bplist00.....YeventPort.........ZtimingPort....
    . +................................
    ```

    To reply this request, just construct a binary plist with the following structure:
    ```json
    {
        eventPort: 0;
        timingPort: xxxx    // The local port of time syncing client
    }
    ```

2. The sender delivers **GET /info RTSP/1.0** request to server

    **Request:** 
    ```
    GET /info RTSP/1.0
    X-Apple-ProtocolVersion: 1
    CSeq: 4
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1
    ```

    This request is querying the capacities of the server and no data need to pares in the request. 

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 4
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 952
    Content-Type: application/x-apple-binary-plist

    bplist00.......	.
    ......"-....
    ........#.XdeviceID\AABBCCDDEEFFXfeatures.R..._..keepAliveLowPower.._..keepAliveSendStatsAsBody..ZmacAddress_..AA:BB:CC:DD:EE:FFUmodelZAppleTV3,2Tname_..APS[AA:BB:CC:DD:EE:FF]]sourceVersionV220.68[statusFlags.DRpi_.$b08f5a79-db29-4384-b456-a4784d9e6055RpkO.@99FD4299889422515FBD27949E4E1E21B2AF50A454499E3D4BE75A4E0F55FE63Rvv..\audioFormats..... ..!Ttype.`_..audioInputFormats....._..audioOutputFormats.....^audioLatencies.$.%')+&(*,Ttype.`YaudioTypeWdefault_..inputLatencyMicros........._..outputLatencyMicros.........Xdisplays./.02468:<>@BD13579;=?ACEXfeatures..Vheight..8\heightPixels..8^heightPhysical.........Uwidth...[widthPixels...]widthPhysical.........[refreshRate#......N@[overscanned.Xrotation.Tuuid_.$e5f7a68d-7b0f-4305-984b-974f677a150b...).2.?.H.M.a.c.~.............................a.d.f.s.u.|.................................&./.1.H.Q.S.Z.].j.m.|...........................................F................
    ```

    To reply this request we need to return a binary plist with the following content:
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

3. The sender delivers **GET_PARAMETER rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    GET_PARAMETER rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 8
    Content-Type: text/parameters
    CSeq: 5
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    volume
    ```

    This request is simply querying the current volume value of the server. 

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 5
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 18
    Content-Type: text/parameters

    volume: 0.000000
    ```

    Just return a text with the above format to tell the sender the volume value.

4. The sender delivers **RECORD rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    RECORD rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    CSeq: 6
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1
    ```

    This request tells the server to start audio syncing process. After receive this request, the sever needs to send a query request from the time sync client to the sender.

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Latency: 0
    CSeq: 6
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

    In response of this request we need to add an HTTP header *Audio-Latency*, the value can be set to 0.

5. The sender delivers **SET_PARAMETER rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    SET_PARAMETER rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 20
    Content-Type: text/parameters
    CSeq: 7
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    volume: -20.000000
    ```
    
    This request tells the sever to set the volume value, note that the volume value range is [-144.0f ~ 0.0f]. We need to convert this value to the ratio which is recognized to the platform the server is running on.

    **Response**
    ```
    RTSP/1.0 200 OK
    CSeq: 7
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

    Just rely it with status code 200, no extra data.

6. The sender delivers **SETUP rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    SETUP rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 188
    Content-Type: application/x-apple-binary-plist
    CSeq: 8
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    bplist00...Wstreams.........Ttype]timestampInfo_..streamConnectionID.n.	.....
    .TnameUSubSu.

    UBePxT.
    .UAfPxT.
    .UBefEn.
    .UEmEnc.j.^..MLr.....!/DFLOTZ]cfloux~................................
    ```

    This request tells the server the video stream information.
    ```json
    {
      streams = [{
        type = 110;
        streamConnectionID = 3873339193950750702;
        timestampInfo = [
          { name = SubSu; },
          { name = BePxT; },
          { name = AfPxT; },
          { name = BefEn; },
          { name = EmEnc; }
        ];
      }];
    }
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 8
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 102
    Content-Type: application/x-apple-binary-plist

    bplist00.....YeventPort...Wstreams......	Ttype.nXdataPort....
    .."$).09...............
    ...............<
    ```

7. The sender delivers **SET_PARAMETER rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server
   
    This is the same process with the step 5.

    **Request:** 
    ```
    SET_PARAMETER rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 20
    Content-Type: text/parameters
    CSeq: 9
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    volume: -20.000000
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    CSeq: 9
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

8. The sender delivers **SETUP rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    SETUP rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 265
    Content-Type: application/x-apple-binary-plist
    CSeq: 10
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    bplist00...Wstreams........	
    ..
    ..............[usingScreen[audioFormat_..supportsDynamicStreamID^redundantAudioYaudioModeRctSspfZlatencyMaxTtype[controlPortWisMediaZlatencyMin	.....	..Wdefault.........`...	.....:F`oy|................................................
    ```

    This request tells the server the video stream information
    ```json
    {
      streams = ({
        audioFormat = 262144;
        audioMode = default;
        controlPort = 54956;
        ct = 2;
        latencyMax = 88200;
        latencyMin = 11025;
        spf = 352;
        type = 96;
      });
    }
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 10
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 104
    Content-Type: application/x-apple-binary-plist

    bplist00...Wstreams........	Ttype.`XdataPort..l[controlPort..m.....!#,/;...............
    ...............>
    ```

9.  The sender delivers **SET_PARAMETER rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    SET_PARAMETER rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 20
    Content-Type: text/parameters
    CSeq: 11
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    volume: -20.000000
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    CSeq: 11
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

10. The sender delivers **FLUSH rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server
    **Request:** 
    ```
    FLUSH rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    RTP-Info: seq=58942;rtptime=1054215198
    CSeq: 12
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 12
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    Content-Type: application/x-apple-binary-plist
    ```
    
---

After the flush request, the session moves into media data transfer state. The sender will push the audio/video data to the server, and also the sender will deliver feedback request periodically with 2 seconds interval.

\>>>>>>>>>>>>>>>> Media Data Transfer >>>>>>>>>>>>>>>>

\<<<<<<<<<<<<<<<<   Media   Feedback  <<<<<<<<<<<<<<<<

\>>>>>>>>>>>>>>>> Media Data Transfer >>>>>>>>>>>>>>>>

\<<<<<<<<<<<<<<<<   Media   Feedback  <<<<<<<<<<<<<<<<

\>>>>>>>>>>>>>>>> Media Data Transfer >>>>>>>>>>>>>>>>

\<<<<<<<<<<<<<<<<   Media   Feedback  <<<<<<<<<<<<<<<<

The sender delivers **POST /feedback RTSP/1.0** request to server

    **Request:** 
    ```
    POST /feedback RTSP/1.0
    CSeq: 13
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1
    ```

For this feedback request, the server needs do nothing, just give an empty response.

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 13
    Date: Wed May  5 02:31:31 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

---

11. The sender delivers **TEARDOWN rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    TEARDOWN rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 84
    Content-Type: application/x-apple-binary-plist
    CSeq: 15
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    bplist00...Wstreams.......XstreamIDTtype...`.....#(*...............................,
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 15
    Date: Wed May  5 02:31:34 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

12. The sender delivers **TEARDOWN rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    TEARDOWN rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 69
    Content-Type: application/x-apple-binary-plist
    CSeq: 16
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    bplist00...Wstreams.....Ttype.n......................................
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 16
    Date: Wed May  5 02:31:34 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

13. The sender delivers **TEARDOWN rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    TEARDOWN rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    Content-Length: 42
    Content-Type: application/x-apple-binary-plist
    CSeq: 17
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1

    bplist00.................................	
    ```

    **Response**
    ```
    RTSP/1.0 200 OK
    Audio-Jack-Status: Connected; type=digital
    CSeq: 17
    Date: Wed May  5 02:31:34 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```


```