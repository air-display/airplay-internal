# _airplay._tcp

The _airplay._tcp service points to the backend HTTP server instance. AirPlay server must implement this service and publish it with required information. The required fields are as follows:

| Field  | Required  | Description  | Sample Value  |
|---|---|--------------------------------------------|---|
|  deviceId | required | The unique ID of the device  | MAC address |
|  features | required | The server feature flags  |  "0x527FFFF7" |
|  model | required | The receiver device model  | "AppleTV3,2" |
|  srcvers | required | The receiver software version  | "220.68" |
|  vv | required | unknown  | [vv](#vv)  |
|  pi | required | unknown  | [pi](#pi) |
|  pk | required | unknown  | [pk](#pk) |
|  flags | required | The server flags | "0x04" |

- deviceId:
  Mac address is recommended for this value and also recommend to include this value as hex string in the service name. That is to say you can publish the _airplay._tcp service with name like ***APS[AA:BB:CC:DD:EE:FF]***. (If so, please remember to name the _raop._tcp service as ***AABBCCDDEEFF@APS[AA:BB:CC:DD:EE:FF]***)

- features:

  The supported features of this AirPlay server, recommend to use this value "0x527FFFF7". Please refer to this page for detailed information <a href="https://nto.github.io/AirPlay.html#servicediscovery-airplayservice" target="_blank">Feature Bit Table</a>

- model:

  The device mode of the AirPlay server, recommend to use "AppleTV3,2"

- srcvers:

  The server software version, recommend to use "220.68"

- <a name="vv">vv</a>:
  
  Set to fixed value "2"

- <a name="pi">pi</a>:
  
  Set to fixed value "b08f5a79-db29-4384-b456-a4784d9e6055", or you can try other values but need to be GUID string

- <a name="pk">pk</a>:

  Set to fixed value "99FD4299889422515FBD27949E4E1E21B2AF50A454499E3D4BE75A4E0F55FE63", or you can try other values

- flags:

  Set to fixed value "0x04"