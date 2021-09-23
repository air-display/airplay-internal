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
    ```

4. The sender delivers **RECORD rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

    **Request:** 
    ```
    RECORD rtsp://192.168.31.82/5259802854977588516 RTSP/1.0
    CSeq: 6
    DACP-ID: 7136391BB370A579
    Active-Remote: 354444643
    User-Agent: AirPlay/425.1
    ```

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

    **Response**
    ```
    RTSP/1.0 200 OK
    CSeq: 7
    Date: Wed May  5 02:31:29 2021 GMT
    Server: AirTunes/220.68
    Session: CAFEBABE
    Content-Length: 0
    ```

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

9. The sender delivers **SET_PARAMETER rtsp://xxx.xxx.xxx.xxx/xxxxxxxxxx RTSP/1.0** request to server

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

After the flush request, the session moves into media data transfer state. The sender will push the audio/video data to the server, and also the sender will deliver feedback request periodically with 2 seconds intervale.
    Media Data Transfer

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