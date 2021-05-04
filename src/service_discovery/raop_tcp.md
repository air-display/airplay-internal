# _raop._tcp

The _raop_._tcp service is pointing to the backend RTSP server instance. And the fields below must be included in the published service.

| Field  | Required  | Description  | Sample Value  |
|---|---|--------------------------------------------|---|
|  am | required | The device model  | "AppleTV3,2" |
|  cn | required | The supported audio codecs  | "0,1,2,3" |
|  et | required | The supported encryption types  | "0,3,5" |
|  ft | required | The supported features  | "0x527FFFF7" |
|  pk | required | unknown  | The same with _airplay._tcp service |
|  tp | required | The transmission protocol "TCP" or "UDP"  |  |
|  vs | required | The server software version  | "220.68" |
|  vv | required | unknown  | The same with _airplay._tcp service |
|  vn | required | unknown  | "65537" |
|  da | required | unknown  | "true" |
|  sf | required | unknown  | "0x04" |

most of the fields are described in the <a href="https://nto.github.io/AirPlay.html#servicediscovery-airtunesservice" target="_blank">AirTunes Service</a> section.
