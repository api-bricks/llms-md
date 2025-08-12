Get symbol funding rate metric data using CoinAPI | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/get-symbol-funding-rate-metric-data)

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
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)

  + [Introduction](/market-data/how-to-guides/)
  + [Acquire exchange rates with different programming languages](/market-data/how-to-guides/acquire-exchange-rates-with-different-programming-languages)
  + [Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react)
  + [Building a cryptocurrency exchange comparison tool using Market Data API](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api)
  + [Creating a historical crypto price chart using CoinAPI and D3.js](/market-data/how-to-guides/creating-historical-crypto-price-chart-using-CoinAPI-and-D3-js)
  + [Fetching market data with KNIME](/market-data/how-to-guides/fetching-market-data-with-knime)
  + [Get Historical OHLCV Data Using CoinAPI](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi)
  + [Get symbol funding rate metric data using CoinAPI](/market-data/how-to-guides/get-symbol-funding-rate-metric-data)
  + [Import API into Postman](/market-data/how-to-guides/import-api-into-postman)
  + [Import data to Google Sheets/Excel](/market-data/how-to-guides/import-data-to-google-sheets-excel)
  + [Real-time data visualization with javascript](/market-data/how-to-guides/real-time-data-visualization-with-javascript)
  + [Real-time trades stream using WebSocket with different languages](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages)
  + [Retrieve and analyze crypto order book data using a cryptocurrency API](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [How-to guides](/market-data/how-to-guides/)
* Get symbol funding rate metric data using CoinAPI

On this page

Get symbol funding rate metric data using CoinAPI
=================================================

This comprehensive tutorial guides you through the process of retrieving current metric data from the example exchange using an API. Whether you're a developer, data analyst, or trader, having access to real-time metrics is crucial for making informed decisions.

Introduction[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#introduction "Direct link to Introduction")
--------------------------------------------------------------------------------------------------------------------------

The API we'll be working with provides access to a wide range of real-time metrics for various symbols and exchanges. You can use this API to fetch current metrics for specific metric identifiers, symbol identifiers, and exchange identifiers.

Understanding the API Endpoints[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#understanding-the-api-endpoints "Direct link to Understanding the API Endpoints")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Let's dive into the details of the API endpoints that allow you to access current metric data:

### /v1/metrics/symbol/listing[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#v1metricssymbollisting "Direct link to /v1/metrics/symbol/listing")

**HTTP Method:** GET

**Summary:** Listing of all supported metrics for symbol

**Description:** This endpoint enables you to retrieve a comprehensive listing of all the supported metrics available for a specific symbol. It's a valuable resource to understand the types of metrics you can access.

**Parameters:**

* `metric_id` (query): Metric identifier (type: string)
* `exchange_id` (query): Exchange identifier (type: string)
* `symbol_id` (query): Symbol identifier (type: string)

**Responses:**

* `200`: Successful operation
  + `text/plain`, `application/json`, `text/json`, `application/x-msgpack`: Array of [ListingItem](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#listingitem)

**Example Request:**

```
GET /v1/metrics/symbol/listing?exchange_id=BINANCEFTSC
```

> The above command returns JSON structured like this:

```
[  
    {  
        "metric_id": "DERIVATIVES_MARK_PRICE",  
        "symbol_id": "BINANCEFTSC_PERP_ETH_USD",  
        "symbol_id_external": "ETHUSD_PERP",  
        "exchange_id": "BINANCEFTSC"  
    },  
    {  
        "metric_id": "DERIVATIVES_FUNDING_RATE_CURRENT",  
        "symbol_id": "BINANCEFTSC_PERP_LTC_USD",  
        "symbol_id_external": "LTCUSD_PERP",  
        "exchange_id": "BINANCEFTSC"  
    },  
    {  
        "metric_id": "LIQUIDATION_AVERAGE_PRICE",  
        "symbol_id": "BINANCEFTSC_PERP_OP_USD",  
        "symbol_id_external": "OPUSD_PERP",  
        "exchange_id": "BINANCEFTSC"  
    },  
    {  
        "metric_id": "LIQUIDATION_ORDER_STATUS",  
        "symbol_id": "BINANCEFTSC_FTS_BCH_USD_231229",  
        "symbol_id_external": "BCHUSD_231229",  
        "exchange_id": "BINANCEFTSC"  
    }  
]
```

### /v1/metrics/symbol/current[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#v1metricssymbolcurrent "Direct link to /v1/metrics/symbol/current")

**HTTP Method:** GET

**Summary:** Current metrics for a given symbol

**Description:** Use this endpoint to fetch real-time metrics for a specific symbol. Whether you're interested in price, volume, or other key metrics, this endpoint provides up-to-the-minute data.

**Parameters:**

* `metric_id` (query): Metric identifier (type: string)
* `symbol_id` (query): Symbol identifier (type: string)
* `exchange_id` (query): Exchange identifier (type: string)

**Responses:**

* `200`: Successful operation
  + `text/plain`, `application/json`, `text/json`, `application-x-msgpack`: Array of [GeneralData](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#generaldata)

**Example Request:**

```
GET /v1/metrics/symbol/current?metric_id=DERIVATIVES_FUNDING_RATE_CURRENT&symbol_id=BINANCEFTSC_PERP_ETH_USD&exchange_id=BINANCEFTSC
```

> The above command returns JSON structured like this:

```
[  
    {  
        "entry_time": "2023-10-17T14:59:00.0828571Z",  
        "recv_time": "2023-10-17T14:59:00.0819390Z",  
        "exchange_id": "BINANCEFTSC",  
        "symbol_id": "BINANCEFTSC_PERP_ETH_USD",  
        "metric_id": "DERIVATIVES_FUNDING_RATE_CURRENT",  
        "value_decimal": 0.00000269  
    }  
]
```

### /v1/metrics/symbol/history[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#v1metricssymbolhistory "Direct link to /v1/metrics/symbol/history")

**HTTP Method:** GET

**Summary:** Historical metrics for a symbol

**Description:** If you need historical metric data for a symbol, this endpoint has you covered. You can specify the time range, format, and limit the number of data points returned.

**Parameters:**

* `metric_id` (query, required): Metric identifier (type: string)
* `symbol_id` (query, required): Symbol identifier (type: string)
* `time_start` (query): Starting time in ISO 8601 format (type: string, format: date-time)
* `time_end` (query): Ending time in ISO 8601 format (type: string, format: date-time)
* `time_format` (query): If set, returned values will be in the Unix timestamp format (valid values: unix\_sec, unix\_millisec, unix\_microsec, unix\_nanosec) (type: string)
* `period_id` (query): Identifier of the requested time series period (e.g., `5SEC` or `2MTH`) (type: string)
* `limit` (query): Amount of items to return (optional, the minimum is 1, the maximum is 100000, the default value is 100, if the parameter is used then every 100 output items are counted as one request) (type: integer, format: int32, default: 100)

**Responses:**

* `200`: Successful operation
  + `text/plain`, `application/json`, `text/json`, `application-x-msgpack`: Array of [MetricData](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#metricdata)

**Example Request:**

```
GET /v1/metrics/symbol/history?metric_id=DERIVATIVES_FUNDING_RATE_CURRENT&symbol_id=BINANCEFTSC_PERP_ETH_USD&time_start=2023-03-01T00:00:00&time_end=2023-03-10T00:00:00&time_format=unix_sec&period_id=1HRS&limit=100
```

> The above command returns JSON structured like this:

```
[  
    {  
        "time_period_start": 1677628800,  
        "time_period_end": 1677632400,  
        "time_open": 1677628800,  
        "time_close": 1677632340,  
        "first": -0.00013075,  
        "last": -0.00011917,  
        "min": -0.00013373,  
        "max": -0.00011458,  
        "count": 57,  
        "sum": -0.00702479  
    },  
    {  
        "time_period_start": 1677632400,  
        "time_period_end": 1677636000,  
        "time_open": 1677632400,  
        "time_close": 1677635940,  
        "first": -0.00011952,  
        "last": -9.289E-05,  
        "min": -0.0001221,  
        "max": -9.267E-05,  
        "count": 57,  
        "sum": -0.006305099999999999  
    },  
    {  
        "time_period_start": 1677636000,  
        "time_period_end": 1677639600,  
        "time_open": 1677636003,  
        "time_close": 1677639540,  
        "first": -9.265E-05,  
        "last": -5.219E-05,  
        "min": -9.265E-05,  
        "max": -5.219E-05,  
        "count": 56,  
        "sum": -0.004191260000000001  
    },  
    {  
        "time_period_start": 1677639600,  
        "time_period_end": 1677643200,  
        "time_open": 1677639600,  
        "time_close": 1677643143,  
        "first": -5.016E-05,  
        "last": 4.839E-05,  
        "min": -5.016E-05,  
        "max": 4.839E-05,  
        "count": 57,  
        "sum": -4.3300000000000144E-06  
    },  
    {  
        "time_period_start": 1677643200,  
        "time_period_end": 1677646800,  
        "time_open": 1677643260,  
        "time_close": 1677645000,  
        "first": 5.084E-05,  
        "last": 0.0001,  
        "min": 5.084E-05,  
        "max": 0.0001,  
        "count": 29,  
        "sum": 0.00223415  
    }  
]
```

Best Practices[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#best-practices "Direct link to Best Practices")
--------------------------------------------------------------------------------------------------------------------------------

To ensure a smooth experience while using this API, consider the following best practices:

* **Secure Your API Keys**: Always store API keys securely and avoid hard-coding them in your code.
* **Rate Limiting**: Be aware of rate limits and handle rate limit-exceeded responses (HTTP 429) gracefully.
* **Efficient Data Fetching**: Use query parameters effectively to retrieve the data you need without unnecessary requests.

Troubleshooting[​](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#troubleshooting "Direct link to Troubleshooting")
-----------------------------------------------------------------------------------------------------------------------------------

If you encounter any issues while working with this API, here are some troubleshooting tips:

* **API Key**: Ensure your API key is correct and has the necessary permissions.
* **Rate Limits**: Stay within the rate limits for your account type to avoid rate limit exceeded responses.
* **Endpoint and Headers**: Use the correct endpoint and provide proper request headers.
* **Parameter Validity**: Verify the validity and format of symbol and period IDs.
* **Dependencies**: Ensure you have the required libraries or dependencies installed.

For more detailed information, refer to the API documentation.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Get Historical OHLCV Data Using CoinAPI](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi)[Next

Import API into Postman](/market-data/how-to-guides/import-api-into-postman)

* [Introduction](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#introduction)
* [Understanding the API Endpoints](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#understanding-the-api-endpoints)
  + [/v1/metrics/symbol/listing](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#v1metricssymbollisting)
  + [/v1/metrics/symbol/current](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#v1metricssymbolcurrent)
  + [/v1/metrics/symbol/history](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#v1metricssymbolhistory)
* [Best Practices](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#best-practices)
* [Troubleshooting](/market-data/how-to-guides/get-symbol-funding-rate-metric-data#troubleshooting)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.