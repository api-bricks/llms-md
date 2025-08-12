List all periods | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/ohlcv/list-all-periods)

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

  + [Introduction](/market-data/rest-api/)
  + [Exchange Rates](/market-data/rest-api/exchange-rates/)
  + [Metadata](/market-data/rest-api/metadata/)
  + [MetricsV1](/market-data/rest-api/metricsv1/)
  + [MetricsV2](/market-data/rest-api/metricsv2/)
  + [Ohlcv](/market-data/rest-api/ohlcv/)

    - [Introduction](/market-data/rest-api/ohlcv/coinapi-market-data-rest-api)
    - [Historical data by exchange](/market-data/rest-api/ohlcv/historical-data-by-exchange)
    - [Historical data](/market-data/rest-api/ohlcv/historical-data)
    - [Latest data](/market-data/rest-api/ohlcv/latest-data)
    - [List all periods](/market-data/rest-api/ohlcv/list-all-periods)
  + [Options](/market-data/rest-api/options/)
  + [Order Book](/market-data/rest-api/order-book/)
  + [Order Book L3](/market-data/rest-api/order-book-l3/)
  + [Quotes](/market-data/rest-api/quotes/)
  + [Trades](/market-data/rest-api/trades/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* REST API
* [Ohlcv](/market-data/rest-api/ohlcv/)
* List all periods

List all periods
================

```
GET

/v1/ohlcv/periods
-----------------
```

Get full list of supported time periods available for requesting OHLCV timeseries data.

### Available periods[​](/market-data/rest-api/ohlcv/list-all-periods#available-periods "Direct link to Available periods")

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

Responses[​](/market-data/rest-api/ohlcv/list-all-periods#responses "Direct link to Responses")
-----------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json
* application/x-msgpack

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

Latest data](/market-data/rest-api/ohlcv/latest-data)[Next

Options](/market-data/rest-api/options/)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.