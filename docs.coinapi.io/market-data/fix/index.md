FIX API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/fix/)

* [Market Data](/market-data/)
* [Exchange Rates](/exchange-rates-api/)
* [EMS](/ems-api/)
* [Indexes](/indexes-api/)
* [Flat Files](/flat-files-api/)
* [NAAS](/naas-api/)

[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.coinapi.io)

Search

[Get a free API Key](https://console.coinapi.io/?link=/apikeys/create)

* [Market Data API](/market-data/)
* [Authentication](/market-data/authentication)
* [API limits and billing](/market-data/api-limits-and-billing-metrics)
* [Metadata Tables](/market-data/metadata-tables/introduction)
* [REST API](/market-data/rest-api/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)

  + [FIX API](/market-data/fix/)
  + [Messages](/market-data/fix/messages)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* FIX API

On this page

FIX API
=======

Market Data - FIX API
=====================

Financial Information eXchange (FIX) protocol is an electronic communications protocol initiated in 1992 for international real-time exchange of information related to the securities transactions and markets.
You can use it to receive real-time market data from us and it's an alternative to WebSocket protocol.

info

If you don't have experience with FIX protocol, consider using a much simpler to implement REST or WebSocket API.

Implemented Standards:

* [FIX4.4](https://www.fixtrading.org/standards/fix-4-4/)

Endpoints[​](/market-data/fix/#endpoints "Direct link to Endpoints")
--------------------------------------------------------------------

| Enviroment | Encryption | Value | Region |
| --- | --- | --- | --- |
| Production | Yes | `fix.coinapi.io:3303` | GeoDNS (auto-routing) |
| Production | No | `fix.coinapi.io:3302` | GeoDNS (auto-routing) |
| Production | Yes | `api-ncsa.coinapi.io:3303` | North & South America |
| Production | No | `api-ncsa.coinapi.io:3302` | North & South America |
| Production | Yes | `api-emea.coinapi.io:3303` | Europe, Middle East & Africa |
| Production | No | `api-emea.coinapi.io:3302` | Europe, Middle East & Africa |
| Production | Yes | `api-apac.coinapi.io:3303` | Asia Pacific |
| Production | No | `api-apac.coinapi.io:3302` | Asia Pacific |

info

The default endpoints (`fix.coinapi.io`) use GeoDNS to automatically route your connections to the nearest datacenter. If you prefer to use a specific region, you can use the region-specific endpoints listed above.

> FIX client configuration file for encrypted connection:

```
[DEFAULT]  
ConnectionType=initiator  
ReconnectInterval=2  
FileStorePath=store  
FileLogPath=log  
StartTime=00:00:00  
EndTime=00:00:00  
NonStopSession=Y  
UseDataDictionary=Y  
ValidateFieldsOutOfOrder=N  
DataDictionary=FIX44.xml  
SocketConnectHost=fix.coinapi.io  
SocketConnectPort=3303  
SSLEnable=Y  
SSLServerName=fix.coinapi.io  
SSLValidateCertificates=Y  
SSLCheckCertificateRevocation=Y  
LogoutTimeout=5  
ResetOnLogon=Y  
ResetOnLogout=Y  
ResetOnDisconnect=Y  
  
[SESSION]  
BeginString=FIX.4.4  
SenderCompID=YOUR_API_KEY  
TargetCompID=COINAPI_V2  
HeartBtInt=10
```

> FIX client configuration file for unencrypted connection:

```
[DEFAULT]  
ConnectionType=initiator  
ReconnectInterval=2  
FileStorePath=store  
FileLogPath=log  
StartTime=00:00:00  
EndTime=00:00:00  
NonStopSession=Y  
UseDataDictionary=Y  
ValidateFieldsOutOfOrder=N  
DataDictionary=FIX44.xml  
SocketConnectHost=fix.coinapi.io  
SocketConnectPort=3302  
SSLEnable=N  
LogoutTimeout=5  
ResetOnLogon=Y  
ResetOnLogout=Y  
ResetOnDisconnect=Y  
  
[SESSION]  
BeginString=FIX.4.4  
SenderCompID=YOUR_API_KEY  
TargetCompID=COINAPI_V2  
HeartBtInt=10
```

Our production endpoint configuration parameters:

| Parameter | Value |
| --- | --- |
| Protocol version | FIX.4.4 *(XML FIX Specification can be downloaded here: [FIX44.xml](https://raw.githubusercontent.com/connamara/quickfixn/master/spec/fix/FIX44.xml))* |
| Gateway timezone | UTC |

We recommend using our SDK or listed client libraries depending on your language requirements:

| Language | Libraries |
| --- | --- |
| C++ | <https://github.com/quickfix/quickfix> |
| C# | [https://github.com/api-bricks/api-bricks-sdk/tree/master/csharp-fix](https://github.com/api-bricks/api-bricks-sdk/tree/master/coinapi/market-data-api-fix/sdk/csharp-fix) <https://github.com/connamara/quickfixn> |
| Java | <https://github.com/quickfix-j/quickfixj> |
| Python | <https://github.com/quickfix/quickfix/tree/master/src/python> |
| Ruby | <https://github.com/quickfix/quickfix/tree/master/src/ruby> |
| Go | [https://github.com/quickfixgo/quickfix/](https://github.com/quickfixgo/quickfix) |

Security[​](/market-data/fix/#security "Direct link to Security")
-----------------------------------------------------------------

> Stunnel configuation:

```
[COINAPI]  
client = yes  
accept = 3302  
connect = fix.coinapi.io:3303  
verify = 2
```

Communication with our FIX gateway is secured by TLS protocol if you are using the encrypted port.
If your FIX protocol implementation does not support establishing a connection over a secure channel,
you must use a proxy between your client and our FIX gateway to unbundle encryption or use the unencrypted port.
We recommend [stunnel](https://www.stunnel.org/) as a proxy if a secure connection can't be established directly from your client and you can't allow unencrypted traffic.

tip

You should assume that we are always providing certificates signed by the Trusted Certification Authority.

oneZero Hub[​](/market-data/fix/#onezero-hub "Direct link to oneZero Hub")
--------------------------------------------------------------------------

Our FIX Connector is passing oneZero Conformance Test. If you need to establish a session using the FIX with your company oneZero Hub, please contact our support at [CoinAPI Support](https://support.coinapi.io/).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

JSON RPC](/market-data/jsonrpc-api)[Next

FIX API](/market-data/fix/)

* [Endpoints](/market-data/fix/#endpoints)
* [Security](/market-data/fix/#security)
* [oneZero Hub](/market-data/fix/#onezero-hub)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.