Estimate daily price for the order | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/rest-api/estimate-daily-price-for-the-order)

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

* [Flat Files](/flat-files-api/)
* [Data & Structure](/flat-files-api/data-types/)
* [Snowflake Access](/flat-files-api/snowflake/)
* [S3 API](/flat-files-api/s3-api/)
* [Push API](/flat-files-api/rest-api/push-api)

  + [Introduction](/flat-files-api/rest-api/push-api)
  + [Metadata](/flat-files-api/rest-api/metadata)
  + [Data Storage](/flat-files-api/rest-api/data-storage)
  + [Orders](/flat-files-api/rest-api/orders)

    - [Calculate price for the order](/flat-files-api/rest-api/calculate-price-for-the-order)
    - [Estimate daily price for the order](/flat-files-api/rest-api/estimate-daily-price-for-the-order)
    - [Create order](/flat-files-api/rest-api/create-order)
    - [List all orders](/flat-files-api/rest-api/list-all-orders)
    - [Delete order](/flat-files-api/rest-api/delete-order)
    - [Account balance](/flat-files-api/rest-api/account-balance)

* [Push API](/flat-files-api/rest-api/push-api)
* [Orders](/flat-files-api/rest-api/orders)
* Estimate daily price for the order

Estimate daily price for the order
==================================

```
POST

/api/push-orders/estimate-daily-price
-------------------------------------
```

Estimate daily price for the order

Request[​](/flat-files-api/rest-api/estimate-daily-price-for-the-order#request "Direct link to Request")
--------------------------------------------------------------------------------------------------------

* application/json
* text/json
* application/\*+json

### Body

required

**id** uuid

**idOrganization** uuid

**exchange** stringrequired

**Possible values:** `<= 255 characters`

**symbols** stringnullable

**schema** stringnullable

**Possible values:** `<= 255 characters`

**date\_from** date-timenullable

**date\_to** date-timenullable

**priceHistorical** double

**priceDailyUpdates** double

**encoding** stringnullable

**Possible values:** `<= 50 characters`

**compression** stringnullable

**Possible values:** `<= 50 characters`

**idDataStorageEndpoint** stringnullable

**Possible values:** `<= 255 characters`

**status** stringnullable

**Possible values:** `<= 255 characters`

**statusDescription** stringnullable

**isDeleted** int32

**createdTime** date-time

**updatedTime** date-time

### Body

required

**id** uuid

**idOrganization** uuid

**exchange** stringrequired

**Possible values:** `<= 255 characters`

**symbols** stringnullable

**schema** stringnullable

**Possible values:** `<= 255 characters`

**date\_from** date-timenullable

**date\_to** date-timenullable

**priceHistorical** double

**priceDailyUpdates** double

**encoding** stringnullable

**Possible values:** `<= 50 characters`

**compression** stringnullable

**Possible values:** `<= 50 characters`

**idDataStorageEndpoint** stringnullable

**Possible values:** `<= 255 characters`

**status** stringnullable

**Possible values:** `<= 255 characters`

**statusDescription** stringnullable

**isDeleted** int32

**createdTime** date-time

**updatedTime** date-time

### Body

required

**id** uuid

**idOrganization** uuid

**exchange** stringrequired

**Possible values:** `<= 255 characters`

**symbols** stringnullable

**schema** stringnullable

**Possible values:** `<= 255 characters`

**date\_from** date-timenullable

**date\_to** date-timenullable

**priceHistorical** double

**priceDailyUpdates** double

**encoding** stringnullable

**Possible values:** `<= 50 characters`

**compression** stringnullable

**Possible values:** `<= 50 characters`

**idDataStorageEndpoint** stringnullable

**Possible values:** `<= 255 characters`

**status** stringnullable

**Possible values:** `<= 255 characters`

**statusDescription** stringnullable

**isDeleted** int32

**createdTime** date-time

**updatedTime** date-time

Responses[​](/flat-files-api/rest-api/estimate-daily-price-for-the-order#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------------------

* 200

OK

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Calculate price for the order](/flat-files-api/rest-api/calculate-price-for-the-order)[Next

Create order](/flat-files-api/rest-api/create-order)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.