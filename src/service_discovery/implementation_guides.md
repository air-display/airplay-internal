# Implementation guides

Since mDNS is not a standard component of all operating systems and it needs to be installed as a system service to work properly, here are some guides for implementing the discovery service of AirPlay server.

## macOS & iOS

For macOS and iOS, there is no need to install any dependencies to publish services through mDNS, because Apple implemented Bonjour service in both macOS and iOS and exposed APIs for leveraging the capacity. For detailed information please refer to <a href="https://developer.apple.com/documentation/foundation/bonjour" target="_blank">NSNetService</a>

   > ⚠️ **NSNetService is deprecated now and will be removed from macOS 12, the alternative API can be found in <a href="https://developer.apple.com/documentation/network/network_functions">Network Framework</a>**



## Windows

For Windows system, <a href="https://developer.apple.com/download/more/?=Bonjour%20SDK%20for%20Windows">Bonjour SDK for Windows</a> is required at both compiling stage and runtime.


## Android

Android system also has a pre-installed mDNS component, so we can implement the discover service without extra dependencies. There are two choices to implement the discovery service. 
1. Framework APIs <a href="https://developer.android.com/training/connect-devices-wirelessly/nsd" target="_blank">Network Service Discovery</a>

2. Native APIs with libdnssd. There is no header files declaring the APIs to access the build-in mDNS components so we need to add the header file in the source repo. Please look into the header file <a href="https://opensource.apple.com/source/mDNSResponder/mDNSResponder-544/mDNSShared/dns_sd.h.auto.html" target="_blank">dns_sd.h</a>.

## Linux

To implement discovery service on Linux system is a bit more complicated, because usually the dns-sd components is not installed. <a href="https://www.avahi.org/" target="_blank">Avahi</a> is recommended. 