FIX API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/fix/)

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

* [EMS API](/ems-api/)
* [Authentication](/ems-api/authentication)
* [API limits and billing](/ems-api/api-limits-and-billing-metrics)
* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)

  + [Introduction](/ems-api/fix/)
  + [Messages](/ems-api/fix/messages)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* FIX API

On this page

FIX API
=======

Financial Information eXchange (FIX) protocol is an electronic communications protocol initiated in 1992 for international real-time exchange of information related to securities transactions and markets.

You can use it for real-time order management and receiving execution reports from us, and it's an alternative to WebSocket protocol.

Implemented Standards:

* [FIX4.4](https://www.fixtrading.org/standards/fix-4-4/)
* [FIX5.0SP2](https://www.fixtrading.org/standards/fix-5-0-sp-2/)
* [FIXT1.1](https://www.fixtrading.org/standards/session-level-specs/)

info

If you don't have experience with FIX protocol, consider using a much simpler to implement REST or WebSocket API.

Endpoints[​](/ems-api/fix/#endpoints "Direct link to Endpoints")
----------------------------------------------------------------

> Default session configuration:

```
[DEFAULT]  
DefaultApplVerID=FIX.5.0  
TransportDataDictionary=FIX/FIXT11.xml  
AppDataDictionary=FIX/FIX50.xml  
ConnectionType=initiator  
ReconnectInterval=1  
ResetOnLogon=Y  
ResetOnLogout=Y  
ResetOnDisconnect=Y  
SenderCompID=OMS.FIX.CLIENT  
SocketConnectPort=3401  
SocketConnectHost=127.0.0.1
```

> `FIX 4.4` session configuration:

```
[SESSION]  
BeginString=FIX.4.4  
StartTime=00:00:00  
EndTime=00:00:00  
TargetCompID=CoinAPI.OEML.FIX  
DataDictionary=FIX/FIX44.xml  
HeartBtInt=1  
FileStorePath=store
```

> `FIX 5.0` / `FIXT 1.1` session configuration:

```
[SESSION]  
BeginString=FIXT.1.1  
StartTime=00:00:00  
EndTime=00:00:00  
TargetCompID=CoinAPI.OEML.FIX  
DataDictionary=FIX/FIX50.xml  
HeartBtInt=1  
FileStorePath=store
```

| Deployment | Environment | Hostname | Port | Authentication |
| --- | --- | --- | --- | --- |
| Managed Cloud | Production | Use [Managed Cloud REST API /v1/locations](#ems-docs-sh) to get specific endpoints to each server site where your deployments span | 3301 | TLS Client Certificate |

Our sesssion configuration parameters:

| Parameter | Value |
| --- | --- |
| Hostname | *look at the table above* |
| Port | *look at the table above* |
| Specifications | \*(XML FIX Specification can be downloaded here: [FIX44.xml](https://raw.githubusercontent.com/connamara/quickfixn/master/spec/fix/FIX44.xml) |
| ) [FIX50.xml](https://raw.githubusercontent.com/coinapi/coinapi-sdk/master/ems-gateway-fix/spec/FIX50.xml) [FIXT11.xml](https://raw.githubusercontent.com/connamara/quickfixn/master/spec/fix/FIXT11.xml))\* |  |
| Gateway timezone | `UTC` |
| ReconnectInterval | `1` |
| ResetOnLogon | `Y` |
| ResetOnLogout | `Y` |
| ResetOnDisconnect | `Y` |
| SenderCompID | `OMS.FIX.CLIENT` |
| TargetCompID | `CoinAPI.OEML.FIX` |
| SocketConnectPort | *look at the table above* |
| StartTime | `00:00:00` |
| EndTime | `00:00:00` |
| HeartBtInt | `1` |

Authentication[​](/ems-api/fix/#authentication "Direct link to Authentication")
-------------------------------------------------------------------------------

As you can observe in the documentation below in the `Logon` FIX Message, it does not contain any authentication data. This is by design.

For our `Managed Cloud` deployment, we require your client to provide us the [certificate](#certificate) from the `Managed Cloud REST API` while establishing a TLS session with us. We use the client certificate provided on the TLS layer to authenticate your FIX session.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Messages](/ems-api/websocket/messages)[Next

Introduction](/ems-api/fix/)

* [Endpoints](/ems-api/fix/#endpoints)
* [Authentication](/ems-api/fix/#authentication)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.