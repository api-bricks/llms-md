Delete account | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/managed-cloud-rest-api/delete-account)

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

  + [Introduction](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
  + [Account](/ems-api/managed-cloud-rest-api/account)

    - [Get accounts](/ems-api/managed-cloud-rest-api/get-account)
    - [Add or update account](/ems-api/managed-cloud-rest-api/persist-account)
    - [Delete account](/ems-api/managed-cloud-rest-api/delete-account)
    - [Delete all accounts](/ems-api/managed-cloud-rest-api/delete-account-all)
  + [Exchange](/ems-api/managed-cloud-rest-api/exchange)
  + [Location](/ems-api/managed-cloud-rest-api/location)
  + [Endpoints](/ems-api/managed-cloud-rest-api/endpoints)
  + [Certificate](/ems-api/managed-cloud-rest-api/certificate)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [Account](/ems-api/managed-cloud-rest-api/account)
* Delete account

Delete account
==============

```
DELETE

/v1/accounts
------------
```

Delete specific exchange account maintained by the EMS API for your subscription.

Request[​](/ems-api/managed-cloud-rest-api/delete-account#request "Direct link to Request")
-------------------------------------------------------------------------------------------

### Query Parameters

**exchange\_id** anyrequired

Exchange identifier of the account to delete

Responses[​](/ems-api/managed-cloud-rest-api/delete-account#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------

* 404

Exchange account not found

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Add or update account](/ems-api/managed-cloud-rest-api/persist-account)[Next

Delete all accounts](/ems-api/managed-cloud-rest-api/delete-account-all)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.