Add datastore endpoint | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/rest-api/add-datastore-endpoint)

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

    - [List all datastore types](/flat-files-api/rest-api/list-all-datastore-types)
    - [List all datastore endpoints](/flat-files-api/rest-api/list-all-datastore-endpoints)
    - [Add datastore endpoint](/flat-files-api/rest-api/add-datastore-endpoint)
    - [Delete datastore endpoint](/flat-files-api/rest-api/delete-datastore-endpoint)
  + [Orders](/flat-files-api/rest-api/orders)

* [Push API](/flat-files-api/rest-api/push-api)
* [Data Storage](/flat-files-api/rest-api/data-storage)
* Add datastore endpoint

Add datastore endpoint
======================

```
POST

/api/data-storage/endpoint
--------------------------
```

Add datastore endpoint

Request[​](/flat-files-api/rest-api/add-datastore-endpoint#request "Direct link to Request")
--------------------------------------------------------------------------------------------

* application/json
* text/json
* application/\*+json

### Body

**id** uuid

**organizationId** uuid

**type** stringrequired

**Possible values:** `<= 255 characters`

**name** stringrequired

**Possible values:** `<= 255 characters`

**url** stringnullable

**Possible values:** `<= 500 characters`

**username** stringnullable

**Possible values:** `<= 255 characters`

**password** stringnullable

**bucket** stringnullable

**Possible values:** `<= 255 characters`

**prefix** stringnullable

**Possible values:** `<= 255 characters`

**region** stringnullable

**Possible values:** `<= 50 characters`

**port** int32nullable

**useSFTP** boolean

**privateKey** stringnullable

**createdTime** date-time

**updatedTime** date-time

**status** stringnullable

**Possible values:** `<= 50 characters`

**statusDescription** stringnullable

**isDeleted** boolean

**timeoutSeconds** int32nullable

**maxConcurrentConnections** int32nullable

**organization**

object

**id** uuid

**stripeId** stringnullable

**name** stringnullable

**quickNodeId** stringnullable

**isDeleting** int32

**company** stringnullable

**country** stringnullable

**address1** stringnullable

**address2** stringnullable

**city** stringnullable

**postalCode** stringnullable

**region** stringnullable

**vatIdType** stringnullable

**vatIdValue** stringnullable

**purchaseOrder** stringnullable

**coupon** stringnullable

**billingEmail** stringnullable

**autoRechargeEnabled** int32

**autoRechargeBalanceGoesBelowUsd** int32

**autoRechargeBalanceBackUpToUsd** int32

**paygEnabled** int32

**creditBalance** int32

**creditUninvoicedCurrent** int32

**creditUninvoicedLimit** int32

### Body

**id** uuid

**organizationId** uuid

**type** stringrequired

**Possible values:** `<= 255 characters`

**name** stringrequired

**Possible values:** `<= 255 characters`

**url** stringnullable

**Possible values:** `<= 500 characters`

**username** stringnullable

**Possible values:** `<= 255 characters`

**password** stringnullable

**bucket** stringnullable

**Possible values:** `<= 255 characters`

**prefix** stringnullable

**Possible values:** `<= 255 characters`

**region** stringnullable

**Possible values:** `<= 50 characters`

**port** int32nullable

**useSFTP** boolean

**privateKey** stringnullable

**createdTime** date-time

**updatedTime** date-time

**status** stringnullable

**Possible values:** `<= 50 characters`

**statusDescription** stringnullable

**isDeleted** boolean

**timeoutSeconds** int32nullable

**maxConcurrentConnections** int32nullable

**organization**

object

**id** uuid

**stripeId** stringnullable

**name** stringnullable

**quickNodeId** stringnullable

**isDeleting** int32

**company** stringnullable

**country** stringnullable

**address1** stringnullable

**address2** stringnullable

**city** stringnullable

**postalCode** stringnullable

**region** stringnullable

**vatIdType** stringnullable

**vatIdValue** stringnullable

**purchaseOrder** stringnullable

**coupon** stringnullable

**billingEmail** stringnullable

**autoRechargeEnabled** int32

**autoRechargeBalanceGoesBelowUsd** int32

**autoRechargeBalanceBackUpToUsd** int32

**paygEnabled** int32

**creditBalance** int32

**creditUninvoicedCurrent** int32

**creditUninvoicedLimit** int32

### Body

**id** uuid

**organizationId** uuid

**type** stringrequired

**Possible values:** `<= 255 characters`

**name** stringrequired

**Possible values:** `<= 255 characters`

**url** stringnullable

**Possible values:** `<= 500 characters`

**username** stringnullable

**Possible values:** `<= 255 characters`

**password** stringnullable

**bucket** stringnullable

**Possible values:** `<= 255 characters`

**prefix** stringnullable

**Possible values:** `<= 255 characters`

**region** stringnullable

**Possible values:** `<= 50 characters`

**port** int32nullable

**useSFTP** boolean

**privateKey** stringnullable

**createdTime** date-time

**updatedTime** date-time

**status** stringnullable

**Possible values:** `<= 50 characters`

**statusDescription** stringnullable

**isDeleted** boolean

**timeoutSeconds** int32nullable

**maxConcurrentConnections** int32nullable

**organization**

object

**id** uuid

**stripeId** stringnullable

**name** stringnullable

**quickNodeId** stringnullable

**isDeleting** int32

**company** stringnullable

**country** stringnullable

**address1** stringnullable

**address2** stringnullable

**city** stringnullable

**postalCode** stringnullable

**region** stringnullable

**vatIdType** stringnullable

**vatIdValue** stringnullable

**purchaseOrder** stringnullable

**coupon** stringnullable

**billingEmail** stringnullable

**autoRechargeEnabled** int32

**autoRechargeBalanceGoesBelowUsd** int32

**autoRechargeBalanceBackUpToUsd** int32

**paygEnabled** int32

**creditBalance** int32

**creditUninvoicedCurrent** int32

**creditUninvoicedLimit** int32

Responses[​](/flat-files-api/rest-api/add-datastore-endpoint#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------

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

List all datastore endpoints](/flat-files-api/rest-api/list-all-datastore-endpoints)[Next

Delete datastore endpoint](/flat-files-api/rest-api/delete-datastore-endpoint)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.