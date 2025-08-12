Timeseries periods | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/exchange-rates/timeseries-periods)

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

    - [Introduction](/market-data/rest-api/exchange-rates/coinapi-market-data-rest-api)
    - [Get all current rates](/market-data/rest-api/exchange-rates/get-all-current-rates)
    - [Get specific rate](/market-data/rest-api/exchange-rates/get-specific-rate)
    - [Timeseries data](/market-data/rest-api/exchange-rates/timeseries-data)
    - [Timeseries periods](/market-data/rest-api/exchange-rates/timeseries-periods)
  + [Metadata](/market-data/rest-api/metadata/)
  + [MetricsV1](/market-data/rest-api/metricsv1/)
  + [MetricsV2](/market-data/rest-api/metricsv2/)
  + [Ohlcv](/market-data/rest-api/ohlcv/)
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
* [Exchange Rates](/market-data/rest-api/exchange-rates/)
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

Timeseries periods[​](/market-data/rest-api/exchange-rates/timeseries-periods#timeseries-periods "Direct link to Timeseries periods")
-------------------------------------------------------------------------------------------------------------------------------------

| Time unit | Period identifiers |
| --- | --- |
| Second | 1SEC, 2SEC, 3SEC, 4SEC, 5SEC, 6SEC, 10SEC, 15SEC, 20SEC, 30SEC |
| Minute | 1MIN, 2MIN, 3MIN, 4MIN, 5MIN, 6MIN, 10MIN, 15MIN, 20MIN, 30MIN |
| Hour | 1HRS, 2HRS, 3HRS, 4HRS, 6HRS, 8HRS, 12HRS |
| Day | 1DAY, 2DAY, 3DAY, 5DAY, 7DAY, 10DAY |

Responses[​](/market-data/rest-api/exchange-rates/timeseries-periods#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------------------

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

Timeseries data](/market-data/rest-api/exchange-rates/timeseries-data)[Next

Metadata](/market-data/rest-api/metadata/)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.