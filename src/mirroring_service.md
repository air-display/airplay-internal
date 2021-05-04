# Mirroring Service

<center>
<a href="images/mirroring-service.png"><img src="images/mirroring-service.png" alt></a>
<br/>
<em>Mirroring Service Interaction Flow</em>
</center>

```
AP Server is starting....
[DEBUG]ap_airplay_connection (000001F561288520) is being created
[DEBUG]Session (000001F561288520) is waiting
[DEBUG]AP service running on 53698
[DEBUG]Session (000001F561297750) is waiting
[DEBUG]Media service running on 53699
AP Server started....
[DEBUG]Session (000001F561288520) accepted and started
[DEBUG]ap_airplay_connection (000001F5612A2FE0) is being created
[DEBUG]Session (000001F5612A2FE0) is waiting
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: GET /info RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 0
        Content-Length: 70
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
        X-Apple-ProtocolVersion: 1
    Body:bplist00?Yqualifier?ZtxtAirPla"
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: POST /fp-setup RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 1
        Content-Length: 16
        Content-Type: application/octet-stream
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
        X-Apple-ET: 32
    Body:FPLY?
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: POST /fp-setup RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 2
        Content-Length: 164
        Content-Type: application/octet-stream
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
        X-Apple-ET: 32
    Body:FPLY??渂A??)~gzⅷ潁丂沃?ˉ旼C賨&A軽S璜伜N?{唈Rx梶p?餉笹島R€鉃芖B0畗?缐啐fV驐?職A央?鶉榜1[^)u?V茫恸l挞e鄄5豷砜饑#犝       籱?T]篨fnDzq?┗
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: SETUP rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 3
        Content-Length: 535
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:bplist00?
etSeiv^timingProtocol[sessionUUIDVosName^osBuildVersion]sourceVersionZtimingPort_isScreenMirroringSessionYosVersionTekeyXdeviceIDUmodelTnameZmacAddress O.?廝,R窦沍┪SNTP_$C498FB03-BFFF-4D09-9DCE-3509E9D378B8XMac OS XV19H524U425.1馠        W10.15.7OHFPLY<f錣E离棛zXCM??躩<??mCT1腴g(籤+#噃   ??s靇88:66:5A:15:D7:E1^MacBookPro16,1_SHEENTIAN-MBP00_88:66:5A:15:D7:E),0?KRaoz??????????%p????
###################on_mirror_session_begin: 3573384831664948512
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: GET /info RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 4
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
        X-Apple-ProtocolVersion: 1
    Body:<EMPTY>
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: GET_PARAMETER rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 5
        Content-Length: 8
        Content-Type: text/parameters
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:volume

[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: RECORD rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 6
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:<EMPTY>
[DEBUG]Timing query packet sent successfully
[DEBUG]Timing reply packet received successfully
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: SET_PARAMETER rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 7
        Content-Length: 20
        Content-Type: text/parameters
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:volume: -20.000000

on_audio_set_volume: 33.3333, value: -20
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: SETUP rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 8
        Content-Length: 188
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:bplist00?Wstreams??Ttype]timestampInfo_streamConnectionIDn??
TnameUSubSu?
UBePxT?
UAfPxT?
UBefEn?
UEmEnc札?rH?!/DFLOTZ]cfloux~?
on_mirror_stream_started
[DEBUG]ap_video_stream_session(000001F56128A7D0) is allocating.
[DEBUG]Session (000001F56128A7D0) is waiting
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: SET_PARAMETER rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 9
        Content-Length: 20
        Content-Type: text/parameters
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:volume: -20.000000

on_audio_set_volume: 33.3333, value: -20
[DEBUG]Session (000001F56128A7D0) accepted and started
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: SETUP rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 10
        Content-Length: 265
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:bplist00?Wstreams??
[usingScreen[audioFormat_supportsDynamicStreamID^redundantAudioYaudioModeRctSspfZlatencyMaxTtype[controlPortWisMediaZlatencyMin       Wdefault??`驅    .:F`oy|€嫄湦刀咐屡仁?
[DEBUG]ap_audio_stream_service (000001F5612B7F10) is being created
on_audio_stream_started: 3
conf_len = 4
  Concealment method was reverted to 1 !
> stream info: channel = 2      sample_rate = 44100     frame_size = 480        aot = 39        bitrate = 0
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: SET_PARAMETER rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 11
        Content-Length: 20
        Content-Type: text/parameters
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:volume: -20.000000

on_audio_set_volume: 33.3333, value: -20
[INFO]audio CONTROL SYNC packet
[INFO]audio CONTROL SYNC packet
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: FLUSH rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 12
        DACP-ID: D8294138B301A2FC
        RTP-Info: seq=54083;rtptime=2288425430
        User-Agent: AirPlay/425.1
    Body:<EMPTY>
on_audio_stream_data: 4, timestamp: 2288419919
on_audio_stream_data: 4, timestamp: 2288420399
on_audio_stream_data: 4, timestamp: 2288420879
on_mirror_stream_heartbeat
on_audio_stream_data: 4, timestamp: 2288421359
on_audio_stream_data: 4, timestamp: 2288421839
on_audio_stream_data: 4, timestamp: 2288422319
on_audio_stream_data: 4, timestamp: 2288422799
on_audio_stream_data: 4, timestamp: 2288423279
on_audio_stream_data: 4, timestamp: 2288423759
on_audio_stream_data: 4, timestamp: 2288424239
on_audio_stream_data: 4, timestamp: 2288424719
on_audio_stream_data: 4, timestamp: 2288425199
on_audio_stream_data: 4, timestamp: 2288425679
on_audio_stream_data: 4, timestamp: 2288426159
on_audio_stream_data: 4, timestamp: 2288426639
on_audio_stream_data: 4, timestamp: 2288427119
on_audio_stream_data: 4, timestamp: 2288427599
on_audio_stream_data: 4, timestamp: 2288428079
on_audio_stream_data: 4, timestamp: 2288428559
on_audio_stream_data: 4, timestamp: 2288429039
on_audio_stream_data: 4, timestamp: 2288429519
on_audio_stream_data: 4, timestamp: 2288429999
on_audio_stream_data: 4, timestamp: 2288430479
on_audio_stream_data: 4, timestamp: 2288430959
on_audio_stream_data: 4, timestamp: 2288431439
on_audio_stream_data: 4, timestamp: 2288431919
on_audio_stream_data: 4, timestamp: 2288432399
on_audio_stream_data: 4, timestamp: 2288432879
on_audio_stream_data: 4, timestamp: 2288433359
on_audio_stream_data: 4, timestamp: 2288433839
on_audio_stream_data: 4, timestamp: 2288434319
on_audio_stream_data: 4, timestamp: 2288434799
on_audio_stream_data: 4, timestamp: 2288435279
on_audio_stream_data: 4, timestamp: 2288435759
on_audio_stream_data: 4, timestamp: 2288436239
on_audio_stream_data: 4, timestamp: 2288436719
on_audio_stream_data: 4, timestamp: 2288437199
on_audio_stream_data: 4, timestamp: 2288437679
on_audio_stream_data: 4, timestamp: 2288438159
on_audio_stream_data: 4, timestamp: 2288438639
on_audio_stream_data: 4, timestamp: 2288439119
on_audio_stream_data: 4, timestamp: 2288439599
on_audio_stream_data: 4, timestamp: 2288440079
on_audio_stream_data: 4, timestamp: 2288440559
on_audio_stream_data: 4, timestamp: 2288441039
on_audio_stream_data: 4, timestamp: 2288441519
on_audio_stream_data: 4, timestamp: 2288441999
on_audio_stream_data: 4, timestamp: 2288442479
on_audio_stream_data: 4, timestamp: 2288442959
on_audio_stream_data: 4, timestamp: 2288443439
on_audio_stream_data: 4, timestamp: 2288443919
on_audio_stream_data: 4, timestamp: 2288444399
on_audio_stream_data: 4, timestamp: 2288444879
on_audio_stream_data: 4, timestamp: 2288445359
on_audio_stream_data: 4, timestamp: 2288445839
on_audio_stream_data: 4, timestamp: 2288446319
on_audio_stream_data: 4, timestamp: 2288446799
on_audio_stream_data: 4, timestamp: 2288447279
on_audio_stream_data: 4, timestamp: 2288447759
on_audio_stream_data: 4, timestamp: 2288448239
on_audio_stream_data: 4, timestamp: 2288448719
on_audio_stream_data: 4, timestamp: 2288449199
on_audio_stream_data: 4, timestamp: 2288449679
on_audio_stream_data: 4, timestamp: 2288450159
on_audio_stream_data: 4, timestamp: 2288450639
on_audio_stream_data: 4, timestamp: 2288451119
on_audio_stream_data: 4, timestamp: 2288451599
on_audio_stream_data: 4, timestamp: 2288452079
on_audio_stream_data: 4, timestamp: 2288452559
on_audio_stream_data: 4, timestamp: 2288453039
on_audio_stream_data: 4, timestamp: 2288453519
on_audio_stream_data: 4, timestamp: 2288453999
on_audio_stream_data: 4, timestamp: 2288454479
on_audio_stream_data: 4, timestamp: 2288454959
on_audio_stream_data: 4, timestamp: 2288455439
on_audio_stream_data: 4, timestamp: 2288455919
on_audio_stream_data: 4, timestamp: 2288456399
on_audio_stream_data: 4, timestamp: 2288456879
on_audio_stream_data: 4, timestamp: 2288457359
on_audio_stream_data: 4, timestamp: 2288457839
on_audio_stream_data: 4, timestamp: 2288458319
on_audio_stream_data: 4, timestamp: 2288458799
on_audio_stream_data: 4, timestamp: 2288459279
on_audio_stream_data: 4, timestamp: 2288459759
on_audio_stream_data: 4, timestamp: 2288460239
on_audio_stream_data: 4, timestamp: 2288460719
on_audio_stream_data: 4, timestamp: 2288461199
on_audio_stream_data: 4, timestamp: 2288461679
on_audio_stream_data: 4, timestamp: 2288462159
on_audio_stream_data: 4, timestamp: 2288462639
on_audio_stream_data: 4, timestamp: 2288463119
[INFO]audio CONTROL SYNC packet
on_audio_stream_data: 4, timestamp: 2288463599
on_audio_stream_data: 4, timestamp: 2288464079
on_mirror_stream_heartbeat
on_audio_stream_data: 4, timestamp: 2288464559
on_audio_stream_data: 4, timestamp: 2288465039
on_audio_stream_data: 4, timestamp: 2288465519
on_audio_stream_data: 4, timestamp: 2288465999
on_audio_stream_data: 4, timestamp: 2288466479
on_audio_stream_data: 4, timestamp: 2288466959
on_audio_stream_data: 4, timestamp: 2288467439
on_audio_stream_data: 4, timestamp: 2288467919
on_audio_stream_data: 4, timestamp: 2288468399
on_mirror_stream_codec:
on_mirror_stream_data payload_size: 1011, timestamp: 0
on_audio_stream_data: 4, timestamp: 2288468879
on_audio_stream_data: 4, timestamp: 2288469359
on_audio_stream_data: 4, timestamp: 2288469839
on_audio_stream_data: 4, timestamp: 2288470319
on_audio_stream_data: 4, timestamp: 2288470799
on_audio_stream_data: 4, timestamp: 2288471279
on_audio_stream_data: 4, timestamp: 2288471759
on_mirror_stream_data payload_size: 72, timestamp: 143165575
on_audio_stream_data: 4, timestamp: 2288472239
on_audio_stream_data: 4, timestamp: 2288472719
on_audio_stream_data: 4, timestamp: 2288473199
on_audio_stream_data: 4, timestamp: 2288473679
on_mirror_stream_data payload_size: 105, timestamp: 286331150
on_mirror_stream_data payload_size: 393, timestamp: 715119098
on_audio_stream_data: 4, timestamp: 2288474159
on_audio_stream_data: 4, timestamp: 2288474639
on_audio_stream_data: 4, timestamp: 2288475119
on_audio_stream_data: 4, timestamp: 2288475599
on_audio_stream_data: 4, timestamp: 2288476079
on_mirror_stream_data payload_size: 2751, timestamp: 1001451769
on_audio_stream_data: 4, timestamp: 2288476559
on_audio_stream_data: 4, timestamp: 2288477039
on_audio_stream_data: 4, timestamp: 2288477519
on_audio_stream_data: 4, timestamp: 2288477999
on_audio_stream_data: 4, timestamp: 2288478479
on_audio_stream_data: 4, timestamp: 2288478959
on_audio_stream_data: 4, timestamp: 2288479439
on_audio_stream_data: 4, timestamp: 2288479919
on_audio_stream_data: 4, timestamp: 2288480399
on_mirror_stream_data payload_size: 65703, timestamp: 1144617344
on_audio_stream_data: 4, timestamp: 2288480879
on_audio_stream_data: 4, timestamp: 2288481359
on_mirror_stream_data payload_size: 44006, timestamp: 1359367607
on_mirror_stream_data payload_size: 53262, timestamp: 1502533943
on_audio_stream_data: 4, timestamp: 2288481839
on_mirror_stream_data payload_size: 10684, timestamp: 1645699518
on_audio_stream_data: 4on_mirror_stream_data payload_size: 4742, timestamp: 1788865093
, timestamp: 2288482319
on_audio_stream_data: 4, timestamp: 2288482799
on_audio_stream_data: 4, timestamp: 2288483279
on_audio_stream_data: 4, timestamp: 2288483759
on_audio_stream_data: 4, timestamp: 2288484239
on_audio_stream_data: 4, timestamp: 2288484719
on_audio_stream_data: 4, timestamp: 2288485199
on_audio_stream_data: 4, timestamp: 2288485679
on_audio_stream_data: 4, timestamp: 2288486159
on_audio_stream_data: 4, timestamp: 2288486639
on_mirror_stream_data payload_size: 4200, timestamp: 1932030668
on_audio_stream_data: 4, timestamp: 2288487119
on_audio_stream_data: 4, timestamp: 2288487599
on_mirror_stream_data payload_size: 4038, timestamp: 2075196243
on_audio_stream_data: 4, timestamp: 2288488079
on_audio_stream_data: 4, timestamp: 2288488559
on_audio_stream_data: 4, timestamp: 2288489039
on_audio_stream_data: 4, timestamp: 2288489519
on_mirror_stream_data payload_size: 4043, timestamp: 2218361818
on_audio_stream_data: 4, timestamp: 2288489999
on_audio_stream_data: 4, timestamp: 2288490479
on_mirror_stream_data payload_size: 4127, timestamp: 2361527393
on_audio_stream_data: 4, timestamp: 2288490959
on_audio_stream_data: 4, timestamp: 2288491439
on_audio_stream_data: 4, timestamp: 2288491919
on_audio_stream_data: 4, timestamp: 2288492399
on_mirror_stream_data payload_size: 4038, timestamp: 2504692968
on_audio_stream_data: 4, timestamp: 2288492879
on_audio_stream_data: 4, timestamp: 2288493359
on_audio_stream_data: 4, timestamp: 2288493839
on_audio_stream_data: 4, timestamp: 2288494319
on_mirror_stream_data payload_size: 4043, timestamp: 2647858543
on_audio_stream_data: 4, timestamp: 2288494799
on_audio_stream_data: 4, timestamp: 2288495279
on_audio_stream_data: 4, timestamp: 2288495759
on_audio_stream_data: 4, timestamp: 2288496239
on_mirror_stream_data payload_size: 4127, timestamp: 2791024118
on_audio_stream_data: 4, timestamp: 2288496719
on_audio_stream_data: 4, timestamp: 2288497199
on_mirror_stream_data payload_size: 4038, timestamp: 2934189694
on_audio_stream_data: 4, timestamp: 2288497679
on_audio_stream_data: 4, timestamp: 2288498159
on_audio_stream_data: 4, timestamp: 2288498639
on_mirror_stream_data payload_size: 4043, timestamp: 3077355269
on_audio_stream_data: 4, timestamp: 2288499119
on_audio_stream_data: 4, timestamp: 2288499599
on_audio_stream_data: 4, timestamp: 2288500079
on_mirror_stream_data payload_size: 4127, timestamp: 3220520844
on_audio_stream_data: 4on_mirror_stream_data payload_size: 4180, timestamp: 3363696302
, timestamp: 2288500559
on_audio_stream_data: 4, timestamp: 2288501039
on_mirror_stream_data payload_size: 4075, timestamp: 3506861877
on_audio_stream_data: 4, timestamp: 2288501519
on_audio_stream_data: 21, timestamp: 2288501999
on_audio_stream_data: 377, timestamp: 2288502479
on_audio_stream_data: 203, timestamp: 2288502959
on_audio_stream_data: 186, timestamp: 2288503439
on_audio_stream_data: 174, timestamp: 2288503919
on_audio_stream_data: 167, timestamp: 2288504399
on_audio_stream_data: 176, timestamp: 2288504879
on_audio_stream_data: 189, timestamp: 2288505359
on_mirror_stream_data payload_size: 4138, timestamp: 3650027452
on_audio_stream_data: 179, timestamp: 2288505839
on_mirror_stream_data payload_size: 4039, timestamp: 3793193027
[INFO]audio CONTROL SYNC packet
on_audio_stream_data: 180, timestamp: 2288506319
on_mirror_stream_data payload_size: 4044, timestamp: 3936358602
on_audio_stream_data: 192, timestamp: 2288506799
on_mirror_stream_heartbeat
on_audio_stream_data: 193, timestamp: 2288507279
on_mirror_stream_data payload_size: 4128, timestamp: 4079524177
on_audio_stream_data: 181, timestamp: 2288507759
on_audio_stream_data: 166, timestamp: 2288508239
on_audio_stream_data: 458, timestamp: 2288508719
on_audio_stream_data: 351, timestamp: 2288509199
on_audio_stream_data: 174, timestamp: 2288509679
on_audio_stream_data: 165, timestamp: 2288510159
on_mirror_stream_data payload_size: 4039, timestamp: 4222689752
on_audio_stream_data: 159, timestamp: 2288510639
on_audio_stream_data: 173, timestamp: 2288511119
on_audio_stream_data: 165, timestamp: 2288511599
on_audio_stream_data: 386, timestamp: 2288512079
on_mirror_stream_data payload_size: 4046, timestamp: 4365855327
on_audio_stream_data: 364, timestamp: 2288512559
on_audio_stream_data: 172, timestamp: 2288513039
on_mirror_stream_data payload_size: 4130, timestamp: 4509020902
on_audio_stream_data: 159, timestamp: 2288513519
on_audio_stream_data: 169, timestamp: 2288513999
on_audio_stream_data: 162, timestamp: 2288514479
on_audio_stream_data: 164, timestamp: 2288514959
on_mirror_stream_data payload_size: 4039, timestamp: 4652186477
on_audio_stream_data: 179, timestamp: 2288515439
on_audio_stream_data: 173, timestamp: 2288515919
on_audio_stream_data: 232, timestamp: 2288516399
on_audio_stream_data: 167, timestamp: 2288516879
on_mirror_stream_data payload_size: 4044, timestamp: 4795352053
on_audio_stream_data: 162, timestamp: 2288517359
on_audio_stream_data: 169, timestamp: 2288517839
on_audio_stream_data: 160, timestamp: 2288518319
on_mirror_stream_data payload_size: 4128, timestamp: 4938517628
on_audio_stream_data: 160, timestamp: 2288518799
on_audio_stream_data: 163, timestamp: 2288519279
on_audio_stream_data: 167, timestamp: 2288519759
on_mirror_stream_data payload_size: 4039, timestamp: 5081683203
on_audio_stream_data: 157, timestamp: 2288520239
on_audio_stream_data: 163, timestamp: 2288520719
on_audio_stream_data: 164, timestamp: 2288521199
on_mirror_stream_data payload_size: 4044, timestamp: 5224848778
on_audio_stream_data: 150, timestamp: 2288521679
on_audio_stream_data: 147, timestamp: 2288522159
on_audio_stream_data: 159, timestamp: 2288522639
on_audio_stream_data: 153, timestamp: 2288523119
on_mirror_stream_data payload_size: 4128, timestamp: 5368014353
on_audio_stream_data: 143, timestamp: 2288523599
on_mirror_stream_data payload_size: 4039, timestamp: 5511179928
on_audio_stream_data: 149, timestamp: 2288524079
on_mirror_stream_data payload_size: 4044, timestamp: 5654345503
on_audio_stream_data: 149, timestamp: 2288524559
on_audio_stream_data: 148, timestamp: 2288525039
on_audio_stream_data: 140, timestamp: 2288525519
on_audio_stream_data: 144, timestamp: 2288525999
on_mirror_stream_data payload_size: 4128, timestamp: 5797511078
on_audio_stream_data: 192, timestamp: 2288526479
on_audio_stream_data: 173, timestamp: 2288526959
on_audio_stream_data: 154, timestamp: 2288527439
on_audio_stream_data: 142, timestamp: 2288527919
on_audio_stream_data: 156, timestamp: 2288528399
on_mirror_stream_data payload_size: 4039, timestamp: 5940676653
on_audio_stream_data: 142, timestamp: 2288528879
on_mirror_stream_data payload_size: 4044, timestamp: 6083842228
on_audio_stream_data: 142, timestamp: 2288529359
on_mirror_stream_data payload_size: 4128, timestamp: 6227007804
on_audio_stream_data: 131, timestamp: 2288529839
on_audio_stream_data: 136, timestamp: 2288530319
on_audio_stream_data: 145, timestamp: 2288530799
on_audio_stream_data: 142, timestamp: 2288531279
on_audio_stream_data: 145, timestamp: 2288531759
on_audio_stream_data: 150, timestamp: 2288532239
on_audio_stream_data: 137, timestamp: 2288532719
on_mirror_stream_data payload_size: 4039, timestamp: 6370173379
on_audio_stream_data: 141, timestamp: 2288533199
on_audio_stream_data: 148, timestamp: 2288533679
on_audio_stream_data: 146, timestamp: 2288534159
on_audio_stream_data: 152, timestamp: 2288534639
on_mirror_stream_data payload_size: 4044, timestamp: 6513338954
on_audio_stream_data: 135, timestamp: 2288535119
on_audio_stream_data: 132, timestamp: 2288535599
on_mirror_stream_data payload_size: 4128, timestamp: 6656504529
on_audio_stream_data: 140, timestamp: 2288536079
on_audio_stream_data: 142, timestamp: 2288536559
on_audio_stream_data: 129, timestamp: 2288537039
on_mirror_stream_data payload_size: 4039, timestamp: 6799670104
on_audio_stream_data: 121, timestamp: 2288537519
on_audio_stream_data: 134, timestamp: 2288537999
on_audio_stream_data: 136, timestamp: 2288538479
on_mirror_stream_data payload_size: 4044, timestamp: 6942835679
on_audio_stream_data: 129, timestamp: 2288538959
on_audio_stream_data: 133, timestamp: 2288539439
on_mirror_stream_data payload_size: 4128, timestamp: 7086001254
on_audio_stream_data: 122, timestamp: 2288539919
on_audio_stream_data: 139, timestamp: 2288540399
on_audio_stream_data: 138, timestamp: 2288540879
on_audio_stream_data: 136, timestamp: 2288541359
on_mirror_stream_data payload_size: 4039, timestamp: 7229166829
on_audio_stream_data: 136, timestamp: 2288541839
on_audio_stream_data: 128, timestamp: 2288542319
on_audio_stream_data: 117, timestamp: 2288542799
on_audio_stream_data: 125, timestamp: 2288543279
on_audio_stream_data: 130, timestamp: 2288543759
on_mirror_stream_data payload_size: 4044, timestamp: 7372332404
on_audio_stream_data: 142, timestamp: 2288544239
on_audio_stream_data: 120, timestamp: 2288544719
on_mirror_stream_data payload_size: 4128, timestamp: 7515497979
on_audio_stream_data: 118, timestamp: 2288545199
on_audio_stream_data: 128, timestamp: 2288545679
on_audio_stream_data: 120, timestamp: 2288546159
on_audio_stream_data: 125, timestamp: 2288546639
on_audio_stream_data: 110, timestamp: 2288547119
on_audio_stream_data: 118, timestamp: 2288547599
on_audio_stream_data: 120, timestamp: 2288548079
on_audio_stream_data: 127, timestamp: 2288548559
on_audio_stream_data: 124, timestamp: 2288549039
on_audio_stream_data: 140, timestamp: 2288549519
on_audio_stream_data: 117, timestamp: 2288549999
on_audio_stream_data: 116, timestamp: 2288550479
on_audio_stream_data: 110, timestamp: 2288550959
on_audio_stream_data: 112, timestamp: 2288551439
on_audio_stream_data: 97, timestamp: 2288551919
on_mirror_stream_heartbeat
[INFO]audio CONTROL SYNC packet
on_audio_stream_data: 47, timestamp: 2288552399
on_audio_stream_data: 22, timestamp: 2288552879
on_audio_stream_data: 21, timestamp: 2288553359
on_audio_stream_data: 18, timestamp: 2288553839
on_audio_stream_data: 4, timestamp: 2288554319
on_audio_stream_data: 4, timestamp: 2288554799
on_audio_stream_data: 4, timestamp: 2288555279
on_audio_stream_data: 4, timestamp: 2288555759
on_audio_stream_data: 4, timestamp: 2288556239
on_audio_stream_data: 4, timestamp: 2288556719
on_audio_stream_data: 4, timestamp: 2288557199
on_audio_stream_data: 4, timestamp: 2288557679
on_audio_stream_data: 4, timestamp: 2288558159
on_audio_stream_data: 4, timestamp: 2288558639
on_audio_stream_data: 4, timestamp: 2288559119
on_audio_stream_data: 4, timestamp: 2288559599
on_audio_stream_data: 4, timestamp: 2288560079
on_audio_stream_data: 4, timestamp: 2288560559
on_audio_stream_data: 4, timestamp: 2288561039
on_audio_stream_data: 4, timestamp: 2288561519
on_audio_stream_data: 4, timestamp: 2288561999
on_audio_stream_data: 4, timestamp: 2288562479
on_audio_stream_data: 4, timestamp: 2288562959
on_audio_stream_data: 4, timestamp: 2288563439
on_audio_stream_data: 4, timestamp: 2288563919
on_audio_stream_data: 4, timestamp: 2288564399
on_audio_stream_data: 4, timestamp: 2288564879
on_audio_stream_data: 4, timestamp: 2288565359
on_audio_stream_data: 4, timestamp: 2288565839
on_audio_stream_data: 4, timestamp: 2288566319
on_audio_stream_data: 4, timestamp: 2288566799
on_audio_stream_data: 4, timestamp: 2288567279
on_audio_stream_data: 4, timestamp: 2288567759
on_audio_stream_data: 4, timestamp: 2288568239
on_audio_stream_data: 4, timestamp: 2288568719
on_audio_stream_data: 4, timestamp: 2288569199
on_audio_stream_data: 4, timestamp: 2288569679
on_audio_stream_data: 4, timestamp: 2288570159
on_audio_stream_data: 4, timestamp: 2288570639
on_audio_stream_data: 4, timestamp: 2288571119
on_audio_stream_data: 4, timestamp: 2288571599
on_audio_stream_data: 4, timestamp: 2288572079
on_audio_stream_data: 4, timestamp: 2288572559
on_audio_stream_data: 4, timestamp: 2288573039
on_audio_stream_data: 4, timestamp: 2288573519
on_audio_stream_data: 4, timestamp: 2288573999
on_audio_stream_data: 4, timestamp: 2288574479
on_mirror_stream_data payload_size: on_audio_stream_data: 4, timestamp: 2288574959
4481, timestamp: 10736762570
on_audio_stream_data: 4, timestamp: 2288575439
on_mirror_stream_data payload_size: 4095, timestamp: 10879928145
on_audio_stream_data: 4, timestamp: 2288575919
on_audio_stream_data: 4, timestamp: 2288576399
on_audio_stream_data: 4, timestamp: 2288576879
on_audio_stream_data: 4, timestamp: 2288577359
on_audio_stream_data: 4, timestamp: 2288577839
on_audio_stream_data: 4, timestamp: 2288578319
on_audio_stream_data: 4, timestamp: 2288578799
on_audio_stream_data: 4, timestamp: 2288579279
on_mirror_stream_data payload_size: 4141, timestamp: 11023093720
on_audio_stream_data: 4, timestamp: 2288579759
on_audio_stream_data: 4, timestamp: 2288580239
on_audio_stream_data: 4, timestamp: 2288580719
on_audio_stream_data: 4, timestamp: 2288581199
on_audio_stream_data: 4, timestamp: 2288581679
on_mirror_stream_data payload_size: 4039, timestamp: 11166259295
on_audio_stream_data: 4, timestamp: 2288582159
on_audio_stream_data: 4, timestamp: 2288582639
on_audio_stream_data: 4, timestamp: 2288583119
on_mirror_stream_data payload_size: 4045, timestamp: 11309424870
on_audio_stream_data: 4, timestamp: 2288583599
on_audio_stream_data: 4, timestamp: 2288584079
on_audio_stream_data: 4, timestamp: 2288584559
on_mirror_stream_data payload_size: 4129, timestamp: 11452590446
on_audio_stream_data: 4, timestamp: 2288585039
on_audio_stream_data: 4, timestamp: 2288585519
on_audio_stream_data: 4, timestamp: 2288585999
on_mirror_stream_data payload_size: 4039, timestamp: 11595756021
on_audio_stream_data: 4, timestamp: 2288586479
on_audio_stream_data: 4, timestamp: 2288586959
on_mirror_stream_data payload_size: 4045, timestamp: 11738921596
on_audio_stream_data: 4, timestamp: 2288587439
on_audio_stream_data: 4, timestamp: 2288587919
on_audio_stream_data: 4, timestamp: 2288588399
on_audio_stream_data: 4, timestamp: 2288588879
on_mirror_stream_data payload_size: 4129, timestamp: 11882087171
on_audio_stream_data: 4, timestamp: 2288589359
on_audio_stream_data: 4, timestamp: 2288589839
on_mirror_stream_data payload_size: 4039, timestamp: 12025252746
on_audio_stream_data: 4, timestamp: 2288590319
on_audio_stream_data: 4, timestamp: 2288590799
on_audio_stream_data: 4, timestamp: 2288591279
on_mirror_stream_data payload_size: 4045, timestamp: 12168418321
on_audio_stream_data: 4, timestamp: 2288591759
on_mirror_stream_data payload_size: 4129, timestamp: 12311583896
on_audio_stream_data: 4, timestamp: 2288592239
on_mirror_stream_data payload_size: 4039, timestamp: on_audio_stream_data: 4, timestamp: 2288592719
12454749471
on_audio_stream_data: 4, timestamp: 2288593199
on_mirror_stream_data payload_size: 4045, timestamp: 12597915046
on_audio_stream_data: 4, timestamp: 2288593679
on_audio_stream_data: 4, timestamp: 2288594159
on_audio_stream_data: 4, timestamp: 2288594639
on_audio_stream_data: 4, timestamp: 2288595119
on_audio_stream_data: 4, timestamp: 2288595599
on_audio_stream_data: 4, timestamp: 2288596079
on_audio_stream_data: 4, timestamp: 2288596559
on_mirror_stream_heartbeat
on_audio_stream_data: 4, timestamp: 2288597039
on_audio_stream_data: 4, timestamp: 2288597519
on_audio_stream_data: 4, timestamp: 2288597999
on_mirror_stream_data payload_size: 4129, timestamp: 12741080621
on_audio_stream_data: 4, timestamp: on_mirror_stream_data payload_size: 4039, timestamp: 12884246197
2288598479
on_mirror_stream_data payload_size: 4045, timestamp: 13027411772
on_audio_stream_data: 4, timestamp: 2288598959
[INFO]audio CONTROL SYNC packet
on_audio_stream_data: 4, timestamp: 2288599439
on_audio_stream_data: 4, timestamp: 2288599919
on_audio_stream_data: 4, timestamp: 2288600399
on_audio_stream_data: 4, timestamp: 2288600879
on_mirror_stream_data payload_size: 4129, timestamp: on_audio_stream_data: 4, timestamp: 2288601359
13170577347
on_audio_stream_data: 4, timestamp: 2288601839
on_audio_stream_data: 4, timestamp: 2288602319
on_audio_stream_data: 4, timestamp: 2288602799
on_mirror_stream_data payload_size: 4039, timestamp: 13313742922
on_audio_stream_data: 4, timestamp: 2288603279
on_audio_stream_data: 4, timestamp: 2288603759
on_audio_stream_data: 4, timestamp: 2288604239
on_audio_stream_data: 4, timestamp: 2288604719
on_mirror_stream_data payload_size: 4045, timestamp: 13456908497
on_audio_stream_data: 4, timestamp: 2288605199
on_audio_stream_data: 4, timestamp: 2288605679
on_mirror_stream_data payload_size: 4129, timestamp: 13600074072on_audio_stream_data: 4, timestamp: 2288606159

on_audio_stream_data: 4, timestamp: 2288606639
on_audio_stream_data: 4, timestamp: 2288607119
on_audio_stream_data: 4, timestamp: 2288607599
on_audio_stream_data: 4, timestamp: 2288608079
on_mirror_stream_data payload_size: 4039, timestamp: 13743239647
on_audio_stream_data: 4, timestamp: 2288608559
on_audio_stream_data: 4, timestamp: 2288609039
on_audio_stream_data: 4, timestamp: 2288609519
on_mirror_stream_data payload_size: 4045, timestamp: 13886405222
on_audio_stream_data: 4, timestamp: 2288609999
on_audio_stream_data: 4, timestamp: 2288610479
on_audio_stream_data: 4, timestamp: 2288610959
on_audio_stream_data: 4, timestamp: 2288611439
on_mirror_stream_data payload_size: 4129, timestamp: 14029570797
on_audio_stream_data: 4, timestamp: 2288611919
on_audio_stream_data: 4, timestamp: 2288612399
on_mirror_stream_data payload_size: 4039, timestamp: 14172736372
on_audio_stream_data: 4, timestamp: 2288612879
on_audio_stream_data: 4, timestamp: 2288613359
on_audio_stream_data: 4, timestamp: 2288613839
on_mirror_stream_data payload_size: 4045, timestamp: 14315901948
on_audio_stream_data: 4, timestamp: 2288614319
on_audio_stream_data: 4, timestamp: 2288614799
on_audio_stream_data: 4, timestamp: 2288615279
on_mirror_stream_data payload_size: 4129, timestamp: 14459067523
on_audio_stream_data: 4, timestamp: 2288615759
on_audio_stream_data: 4, timestamp: 2288616239
on_mirror_stream_data payload_size: 4039, timestamp: on_audio_stream_data: 4, timestamp: 2288616719
14602233098
on_audio_stream_data: 4, timestamp: 2288617199
on_mirror_stream_data payload_size: 4045, timestamp: on_audio_stream_data: 4, timestamp: 2288617679
14745398673
on_audio_stream_data: 4, timestamp: 2288618159
on_audio_stream_data: 4, timestamp: 2288618639
on_audio_stream_data: 4, timestamp: 2288619119
on_mirror_stream_data payload_size: 4129, timestamp: 14888564248
on_audio_stream_data: 4, timestamp: 2288619599
on_audio_stream_data: 4, timestamp: 2288620079
on_audio_stream_data: 4, timestamp: 2288620559
on_audio_stream_data: 4, timestamp: 2288621039
on_audio_stream_data: 4, timestamp: 2288621519
on_audio_stream_data: 4, timestamp: 2288621999
on_audio_stream_data: 4, timestamp: 2288622479
on_audio_stream_data: 4, timestamp: 2288622959
on_audio_stream_data: 4, timestamp: 2288623439
on_audio_stream_data: 4, timestamp: 2288623919
on_audio_stream_data: 4, timestamp: 2288624399
on_audio_stream_data: 4, timestamp: 2288624879
on_audio_stream_data: 4, timestamp: 2288625359
on_audio_stream_data: 4, timestamp: 2288625839
on_audio_stream_data: 4, timestamp: 2288626319
on_audio_stream_data: 4, timestamp: 2288626799
on_audio_stream_data: 4, timestamp: 2288627279
on_audio_stream_data: 4, timestamp: 2288627759
on_audio_stream_data: 4, timestamp: 2288628239
on_mirror_stream_data payload_size: 6237, timestamp: 15890750641
on_audio_stream_data: 4, timestamp: 2288628719
on_audio_stream_data: 4, timestamp: 2288629199
on_audio_stream_data: 4, timestamp: 2288629679
on_audio_stream_data: 4, timestamp: 2288630159
on_audio_stream_data: 4, timestamp: 2288630639
on_mirror_stream_data payload_size: 4339, timestamp: 16033916216
on_audio_stream_data: 4, timestamp: 2288631119
on_audio_stream_data: 4, timestamp: 2288631599
on_audio_stream_data: 4, timestamp: 2288632079
on_audio_stream_data: 4, timestamp: 2288632559
on_mirror_stream_data payload_size: 4176, timestamp: 16177081791
on_audio_stream_data: 4, timestamp: 2288633039
on_audio_stream_data: 4, timestamp: 2288633519
on_audio_stream_data: 4, timestamp: 2288633999
on_audio_stream_data: 4, timestamp: 2288634479
on_audio_stream_data: 4, timestamp: 2288634959
on_mirror_stream_data payload_size: 4044, timestamp: 16320247367
on_audio_stream_data: 4, timestamp: 2288635439
on_audio_stream_data: 4, timestamp: 2288635919
on_audio_stream_data: 4, timestamp: 2288636399
on_mirror_stream_data payload_size: 4050, timestamp: 16463412942
on_audio_stream_data: 4, timestamp: 2288636879
on_audio_stream_data: 4, timestamp: 2288637359
on_mirror_stream_data payload_size: 4134, timestamp: 16606578517
on_audio_stream_data: 4, timestamp: 2288637839
on_mirror_stream_data payload_size: on_audio_stream_data: 4, timestamp: 2288638319
4044, timestamp: 16749744092
on_audio_stream_data: 4, timestamp: 2288638799
on_mirror_stream_data payload_size: 4050, timestamp: 16892909667
on_audio_stream_data: 4, timestamp: 2288639279
on_mirror_stream_heartbeat
on_audio_stream_data: 4, timestamp: 2288639759
on_mirror_stream_data payload_size: 4134, timestamp: on_audio_stream_data: 4, timestamp: 2288640239
17036075242
on_audio_stream_data: 4, timestamp: 2288640719
on_audio_stream_data: 4, timestamp: 2288641199
on_audio_stream_data: 4, timestamp: 2288641679
on_audio_stream_data: 4, timestamp: 2288642159
on_audio_stream_data: 4, timestamp: 2288642639
on_audio_stream_data: 4, timestamp: 2288643119
on_mirror_stream_data payload_size: 4044, timestamp: 17179240817
[INFO]audio CONTROL SYNC packet
on_audio_stream_data: 4, timestamp: 2288643599
on_audio_stream_data: 4, timestamp: 2288644079
on_audio_stream_data: 4, timestamp: on_mirror_stream_data payload_size: 4050, timestamp: 17322406392
2288644559
on_mirror_stream_data payload_size: 4134on_audio_stream_data: 4, timestamp: 2288645039
, timestamp: 17465571967
on_audio_stream_data: 4, timestamp: 2288645519
on_mirror_stream_data payload_size: 4044, timestamp: on_audio_stream_data: 4, timestamp: 2288645999
17608737542
on_audio_stream_data: 4, timestamp: 2288646479
on_audio_stream_data: 4, timestamp: 2288646959
on_audio_stream_data: 4, timestamp: 2288647439
on_audio_stream_data: 4, timestamp: 2288647919
on_audio_stream_data: 4, timestamp: 2288648399
on_audio_stream_data: 4, timestamp: 2288648879
on_audio_stream_data: 4, timestamp: 2288649359
on_audio_stream_data: 4, timestamp: 2288649839
on_mirror_stream_data payload_size: 4050, timestamp: 17751903118
on_audio_stream_data: 4, timestamp: 2288650319
on_audio_stream_data: 4, timestamp: 2288650799
on_mirror_stream_data payload_size: 4134, timestamp: 17895068693
on_audio_stream_data: 4, timestamp: 2288651279
on_audio_stream_data: 4, timestamp: 2288651759
on_audio_stream_data: 4, timestamp: 2288652239
on_mirror_stream_data payload_size: 4044, timestamp: 18038234268
on_audio_stream_data: 4, timestamp: 2288652719
on_audio_stream_data: 4, timestamp: 2288653199
on_mirror_stream_data payload_size: 4050, timestamp: 18181399843
on_audio_stream_data: 4, timestamp: 2288653679
on_audio_stream_data: 4, timestamp: 2288654159
on_audio_stream_data: 4, timestamp: 2288654639
on_mirror_stream_data payload_size: 4134, timestamp: 18324565418
on_audio_stream_data: 4, timestamp: 2288655119
on_audio_stream_data: 4, timestamp: 2288655599
on_mirror_stream_data payload_size: 4044, timestamp: 18467730993
on_audio_stream_data: 4, timestamp: 2288656079
on_audio_stream_data: 4, timestamp: 2288656559
on_audio_stream_data: 4, timestamp: 2288657039
on_audio_stream_data: 4, timestamp: 2288657519
on_mirror_stream_data payload_size: 4050, timestamp: 18610896568
on_audio_stream_data: 4, timestamp: 2288657999
on_audio_stream_data: 4, timestamp: 2288658479
on_audio_stream_data: 4, timestamp: 2288658959
on_audio_stream_data: 4, timestamp: 2288659439
on_mirror_stream_data payload_size: 4134, timestamp: 18754062143
on_audio_stream_data: 4, timestamp: 2288659919
on_audio_stream_data: 4, timestamp: 2288660399
on_audio_stream_data: 4, timestamp: 2288660879
on_audio_stream_data: 4, timestamp: 2288661359
on_mirror_stream_data payload_size: 4044, timestamp: 18897227718
on_audio_stream_data: 4, timestamp: 2288661839
on_audio_stream_data: 4, timestamp: 2288662319
on_audio_stream_data: 4, timestamp: 2288662799
on_mirror_stream_data payload_size: 4050, timestamp: 19040393293
on_audio_stream_data: 4, timestamp: 2288663279
on_mirror_stream_data payload_size: 4134on_audio_stream_data: 4, timestamp: 2288663759
, timestamp: 19183558869
on_audio_stream_data: 4, timestamp: 2288664239
on_mirror_stream_data payload_size: 4044on_audio_stream_data: 4, timestamp: 2288664719
, timestamp: 19326724444
on_audio_stream_data: 4, timestamp: 2288665199
on_audio_stream_data: 4, timestamp: 2288665679
on_audio_stream_data: 4, timestamp: 2288666159
on_audio_stream_data: 4, timestamp: 2288666639
on_mirror_stream_data payload_size: 4050, timestamp: 19469890019
on_audio_stream_data: 4, timestamp: 2288667119
on_mirror_stream_data payload_size: 4134, timestamp: 19613055594
on_audio_stream_data: 4, timestamp: 2288667599
on_mirror_stream_data payload_size: 4044, timestamp: 19756221169
on_audio_stream_data: 4, timestamp: 2288668079
on_mirror_stream_data payload_size: 4050, timestamp: on_audio_stream_data: 4, timestamp: 2288668559
19827824862
on_audio_stream_data: 4, timestamp: 2288669039
on_audio_stream_data: 4, timestamp: 2288669519
on_audio_stream_data: 4, timestamp: 2288669999
on_audio_stream_data: 4, timestamp: 2288670479
on_audio_stream_data: 4, timestamp: 2288670959
on_audio_stream_data: 4, timestamp: 2288671439
on_audio_stream_data: 4, timestamp: 2288671919
on_mirror_stream_data payload_size: 4134, timestamp: 19970990437
on_audio_stream_data: 4, timestamp: 2288672399
on_audio_stream_data: 4, timestamp: 2288672879
on_audio_stream_data: 4, timestamp: 2288673359
on_audio_stream_data: 4, timestamp: 2288673839
on_audio_stream_data: 4, timestamp: 2288674319
on_audio_stream_data: 4, timestamp: 2288674799
on_mirror_stream_data payload_size: 4044, timestamp: 20114156013
on_audio_stream_data: 4, timestamp: 2288675279
on_audio_stream_data: 4, timestamp: 2288675759
on_mirror_stream_data payload_size: 4052, timestamp: 20257321588
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: TEARDOWN rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 16
        Content-Length: 84
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:bplist00?Wstreams??XstreamIDTtype#(*,
[DEBUG]ap_audio_stream_service (000001F5612B7F10) is being destroyed
on_audio_stream_stopped
[DEBUG]Audio stream disconnected
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: TEARDOWN rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 17
        Content-Length: 69
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:bplist00?Wstreams??Ttype
[DEBUG]ap_video_stream_session(000001F56128A7D0) is destroying.
on_mirror_stream_stopped
[DEBUG]Mirroring video stream disconnected
[DEBUG][2153408660768]<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<
    Request: TEARDOWN rtsp://192.168.31.82/14166348621418548489 RTSP/1.0
    Header:
        Active-Remote: 3305977596
        CSeq: 18
        Content-Length: 42
        Content-Type: application/x-apple-binary-plist
        DACP-ID: D8294138B301A2FC
        User-Agent: AirPlay/425.1
    Body:bplist00?
-------------------on_session_end: 3573384831664948512
[DEBUG]ap_airplay_connection (000001F561288520) is being destroyed

```