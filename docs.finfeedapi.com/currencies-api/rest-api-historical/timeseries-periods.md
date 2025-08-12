Timeseries periods | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Currencies API](/currencies-api/)
* [Authentication](/currencies-api/authentication)
* [Metadata Tables](/currencies-api/metadata-tables/introduction)
* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)

  + [Introduction](/currencies-api/rest-api-historical/fx-historical-rest-api)
  + [Exchange Rates](/currencies-api/rest-api-historical/exchange-rates)

    - [Get specific rate](/currencies-api/rest-api-historical/get-specific-rate)
    - [Get all current rates](/currencies-api/rest-api-historical/get-all-current-rates)
    - [Timeseries periods](/currencies-api/rest-api-historical/timeseries-periods)
    - [Timeseries data](/currencies-api/rest-api-historical/timeseries-data)
  + [Metadata](/currencies-api/rest-api-historical/metadata)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Exchange Rates](/currencies-api/rest-api-historical/exchange-rates)
* Timeseries periods

Timeseries periods
==================

```
GET

/v1/exchangerate/history/periods
--------------------------------
```

You can also obtain historical exchange rates of any asset pair, grouped into time periods.
Get full list of supported time periods available for requesting exchange rates historical timeseries data.

Timeseries periods[​](/currencies-api/rest-api-historical/timeseries-periods#timeseries-periods "Direct link to Timeseries periods")
------------------------------------------------------------------------------------------------------------------------------------

| Time unit | Period identifiers |
| --- | --- |
| Second | 1SEC, 2SEC, 3SEC, 4SEC, 5SEC, 6SEC, 10SEC, 15SEC, 20SEC, 30SEC |
| Minute | 1MIN, 2MIN, 3MIN, 4MIN, 5MIN, 6MIN, 10MIN, 15MIN, 20MIN, 30MIN |
| Hour | 1HRS, 2HRS, 3HRS, 4HRS, 6HRS, 8HRS, 12HRS |
| Day | 1DAY, 2DAY, 3DAY, 5DAY, 7DAY, 10DAY |

Responses[​](/currencies-api/rest-api-historical/timeseries-periods#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------------------

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

The period ID.

**length\_seconds** int32

The length of the period in seconds.

**length\_months** int32

The length of the period in months.

**unit\_count** int32nullable

The unit count.

**unit\_name** stringnullable

The unit name.

**display\_name** stringnullable

The display name of the timeseries period.

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
    "period_id": "30MIN",  
    "length_seconds": 1800,  
    "length_months": 0,  
    "unit_count": 30,  
    "unit_name": "minute",  
    "display_name": "30 Minutes"  
  },  
  {  
    "period_id": "10DAY",  
    "length_seconds": 864000,  
    "length_months": 0,  
    "unit_count": 10,  
    "unit_name": "day",  
    "display_name": "10 Days"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**period\_id** stringnullable

The period ID.

**length\_seconds** int32

The length of the period in seconds.

**length\_months** int32

The length of the period in months.

**unit\_count** int32nullable

The unit count.

**unit\_name** stringnullable

The unit name.

**display\_name** stringnullable

The display name of the timeseries period.

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
    "period_id": "30MIN",  
    "length_seconds": 1800,  
    "length_months": 0,  
    "unit_count": 30,  
    "unit_name": "minute",  
    "display_name": "30 Minutes"  
  },  
  {  
    "period_id": "10DAY",  
    "length_seconds": 864000,  
    "length_months": 0,  
    "unit_count": 10,  
    "unit_name": "day",  
    "display_name": "10 Days"  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**period\_id** stringnullable

The period ID.

**length\_seconds** int32

The length of the period in seconds.

**length\_months** int32

The length of the period in months.

**unit\_count** int32nullable

The unit count.

**unit\_name** stringnullable

The unit name.

**display\_name** stringnullable

The display name of the timeseries period.

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
    "period_id": "30MIN",  
    "length_seconds": 1800,  
    "length_months": 0,  
    "unit_count": 30,  
    "unit_name": "minute",  
    "display_name": "30 Minutes"  
  },  
  {  
    "period_id": "10DAY",  
    "length_seconds": 864000,  
    "length_months": 0,  
    "unit_count": 10,  
    "unit_name": "day",  
    "display_name": "10 Days"  
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

Get all current rates](/currencies-api/rest-api-historical/get-all-current-rates)[Next

Timeseries data](/currencies-api/rest-api-historical/timeseries-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.