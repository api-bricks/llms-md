List all periods | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Stock Data API](/stock-api/)
* [Authentication](/stock-api/authentication)
* [Metadata Tables](/stock-api/metadata-tables/introduction)
* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)

  + [Introduction](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
  + [Native IEX](/stock-api/rest-api-historical/get-admin-messages)
  + [Metadata](/stock-api/rest-api-historical/list-of-exchanges)
  + [Ohlcv](/stock-api/rest-api-historical/list-all-periods)

    - [List all periods](/stock-api/rest-api-historical/list-all-periods)
    - [Historical data](/stock-api/rest-api-historical/historical-data)
    - [Historical data by exchange](/stock-api/rest-api-historical/historical-data-by-exchange)
    - [Latest data](/stock-api/rest-api-historical/latest-data)
* [JSON RPC](/stock-api/jsonrpc-api)

* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
* Ohlcv
* List all periods

List all periods
================

```
GET

/v1/ohlcv/periods
-----------------
```

Get full list of supported time periods available for requesting OHLCV timeseries data.

### Available periods[​](/stock-api/rest-api-historical/list-all-periods#available-periods "Direct link to Available periods")

| Time unit | Period identifiers |
| --- | --- |
| Second | 1SEC, 2SEC, 3SEC, 4SEC, 5SEC, 6SEC, 10SEC, 15SEC, 20SEC, 30SEC |
| Minute | 1MIN, 2MIN, 3MIN, 4MIN, 5MIN, 6MIN, 10MIN, 15MIN, 20MIN, 30MIN |
| Hour | 1HRS, 2HRS, 3HRS, 4HRS, 6HRS, 8HRS, 12HRS |
| Day | 1DAY, 2DAY, 3DAY, 5DAY, 7DAY, 10DAY |
| Month | 1MTH, 2MTH, 3MTH, 4MTH, 6MTH |
| Year | 1YRS, 2YRS, 3YRS, 4YRS, 5YRS |

tip

You can assume that we will not remove any periods from this response, however, we may add new ones.

Responses[​](/stock-api/rest-api-historical/list-all-periods#responses "Direct link to Responses")
--------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**period\_id** stringnullable

Gets or sets the period ID.

**length\_seconds** int32

Gets or sets the length of the period in seconds.

**length\_months** int32

Gets or sets the length of the period in months.

**unit\_count** int32nullable

Gets or sets the unit count.

**unit\_name** stringnullable

Gets or sets the unit name.

**display\_name** stringnullable

Gets or sets the display name of the timeseries period.

* ]

```
[  
  {  
    "period_id": "string",  
    "length_seconds": 0,  
    "length_months": 0,  
    "unit_count": 0,  
    "unit_name": "string",  
    "display_name": "string"  
  }  
]
```

```
[  
  {  
    "period_id": "1SEC",  
    "length_seconds": 1,  
    "length_months": 0,  
    "unit_count": 1,  
    "unit_name": "second",  
    "display_name": "1 Second"  
  },  
  {  
    "period_id": "10DAY",  
    "length_seconds": 864000,  
    "length_months": 0,  
    "unit_count": 10,  
    "unit_name": "day",  
    "display_name": "10 Days"  
  },  
  {  
    "period_id": "2YRS",  
    "length_seconds": 0,  
    "length_months": 24,  
    "unit_count": 2,  
    "unit_name": "year",  
    "display_name": "2 Years"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**period\_id** stringnullable

Gets or sets the period ID.

**length\_seconds** int32

Gets or sets the length of the period in seconds.

**length\_months** int32

Gets or sets the length of the period in months.

**unit\_count** int32nullable

Gets or sets the unit count.

**unit\_name** stringnullable

Gets or sets the unit name.

**display\_name** stringnullable

Gets or sets the display name of the timeseries period.

* ]

```
[  
  {  
    "period_id": "string",  
    "length_seconds": 0,  
    "length_months": 0,  
    "unit_count": 0,  
    "unit_name": "string",  
    "display_name": "string"  
  }  
]
```

```
[  
  {  
    "period_id": "1SEC",  
    "length_seconds": 1,  
    "length_months": 0,  
    "unit_count": 1,  
    "unit_name": "second",  
    "display_name": "1 Second"  
  },  
  {  
    "period_id": "10DAY",  
    "length_seconds": 864000,  
    "length_months": 0,  
    "unit_count": 10,  
    "unit_name": "day",  
    "display_name": "10 Days"  
  },  
  {  
    "period_id": "2YRS",  
    "length_seconds": 0,  
    "length_months": 24,  
    "unit_count": 2,  
    "unit_name": "year",  
    "display_name": "2 Years"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**period\_id** stringnullable

Gets or sets the period ID.

**length\_seconds** int32

Gets or sets the length of the period in seconds.

**length\_months** int32

Gets or sets the length of the period in months.

**unit\_count** int32nullable

Gets or sets the unit count.

**unit\_name** stringnullable

Gets or sets the unit name.

**display\_name** stringnullable

Gets or sets the display name of the timeseries period.

* ]

```
[  
  {  
    "period_id": "string",  
    "length_seconds": 0,  
    "length_months": 0,  
    "unit_count": 0,  
    "unit_name": "string",  
    "display_name": "string"  
  }  
]
```

```
[  
  {  
    "period_id": "1SEC",  
    "length_seconds": 1,  
    "length_months": 0,  
    "unit_count": 1,  
    "unit_name": "second",  
    "display_name": "1 Second"  
  },  
  {  
    "period_id": "10DAY",  
    "length_seconds": 864000,  
    "length_months": 0,  
    "unit_count": 10,  
    "unit_name": "day",  
    "display_name": "10 Days"  
  },  
  {  
    "period_id": "2YRS",  
    "length_seconds": 0,  
    "length_months": 24,  
    "unit_count": 2,  
    "unit_name": "year",  
    "display_name": "2 Years"  
  }  
]
```

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

List of symbols for the exchange](/stock-api/rest-api-historical/list-of-symbols-for-the-exchange)[Next

Historical data](/stock-api/rest-api-historical/historical-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.