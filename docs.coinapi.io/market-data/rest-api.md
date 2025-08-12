REST API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/)

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
* Introduction

On this page

Version: v1

REST API
========

RESTful endpoint provides the widest range of data, based on HTTP protocol which works in Request-Reply scheme.

Implemented Standards:

* [HTTP1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP2.0](https://datatracker.ietf.org/doc/html/rfc7540)
* [OpenAPI v3](https://www.openapis.org/)

> **Note:** We adhere to the OpenAPI standards for documenting our API.

OpenAPI Specification[​](/market-data/rest-api/#openapi-specification "Direct link to OpenAPI Specification")
-------------------------------------------------------------------------------------------------------------

To access our API's OpenAPI specification, you can use the following link: [OpenAPI v3](https://raw.githubusercontent.com/coinapi/coinapi-sdk/master/data-api/coinapi-marketdata-rest.yaml)

If you need to import the OpenAPI file into software like Postman, simply copy and paste the link below:

```
https://raw.githubusercontent.com/coinapi/coinapi-sdk/master/data-api/coinapi-marketdata-rest.yaml
```

Endpoints[​](/market-data/rest-api/#endpoints "Direct link to Endpoints")
-------------------------------------------------------------------------

| Enviroment | Encryption | Value | Region |
| --- | --- | --- | --- |
| Production | Yes | `https://rest.coinapi.io/` | GeoDNS (auto-routing) |
| Production | No | `http://rest.coinapi.io/` | GeoDNS (auto-routing) |
| Production | Yes | `https://api-ncsa.coinapi.io/` | North & South America |
| Production | No | `http://api-ncsa.coinapi.io/` | North & South America |
| Production | Yes | `https://api-emea.coinapi.io/` | Europe, Middle East & Africa |
| Production | No | `http://api-emea.coinapi.io/` | Europe, Middle East & Africa |
| Production | Yes | `https://api-apac.coinapi.io/` | Asia Pacific |
| Production | No | `http://api-apac.coinapi.io/` | Asia Pacific |

info

The default endpoints (`rest.coinapi.io`) use GeoDNS to automatically route your requests to the nearest datacenter. If you prefer to use a specific region, you can use the region-specific endpoints listed above.

General[​](/market-data/rest-api/#general "Direct link to General")
-------------------------------------------------------------------

If you want to learn how to authenticate to this API, you can find detailed instructions and guidance in
[authentication section](/authentication) of this documentation.

### HTTP Requests[​](/market-data/rest-api/#http-requests "Direct link to HTTP Requests")

Each HTTP request must contain the header `Accept: application/json` as all our responses are in JSON format.

We encourage you to use the HTTP request header `Accept-Encoding: br, gzip` for all requests.
This will indicate to us that we can deliver compressed data to you which on your side should be decompressed transparently.

tip

By allowing data compression you are lowering bandwidth requirements by approximately 80%.
This is important for requesting large amounts of data or using WebSocket Streaming API,
as we can deliver data to you faster and more effectively.

#### HTTP Success[​](/market-data/rest-api/#http-success "Direct link to HTTP Success")

Successful HTTP responses have the status code `200` and the body in a format according to documentation of the requested resource.

info

You should always check that your HTTP response status code is equal to 200, otherwise the requested was not successful.

#### HTTP Errors[​](/market-data/rest-api/#http-errors "Direct link to HTTP Errors")

> Error message is returned in JSON structured like this:

```
{  
    "error": "Invalid API key"  
}
```

All HTTP requests with response status codes different to `200` must be considered as failed
and you should expect additional JSON inside the body of the response with the error message encapsulated inside it as shown in the example.
We use the following error codes:

| Error Code | Meaning |
| --- | --- |
| 400 | Bad Request -- There is something wrong with your request |
| 401 | Unauthorized -- Your API key is wrong |
| 403 | Forbidden -- Your API key doesnt't have enough privileges to access this resource |
| 429 | Too many requests -- You have exceeded your API key rate limits |
| 550 | No data -- You requested specific single item that we don't have at this moment. |

info

Good practice is to store all error messages somewhere along with request data for further manual review.

### Output data format[​](/market-data/rest-api/#output-data-format "Direct link to Output data format")

By default we are using JSON output data format for all of our endpoints, you can control format of data by using `output_format` variable in query string parameters.

#### URL Parameters[​](/market-data/rest-api/#url-parameters "Direct link to URL Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| output\_format | string | Output data format *(optional, default value is `json`, possible values are `json`, `xml` or `csv`)* |
| csv\_include\_header | bool | Ignore header line in CSV output? *(optional, default value is `true`, `true` to include CSV header line, `false` otherwise)* |
| csv\_include\_quotes | bool | Encapsulate strings with quotes in CSV output? *(optional, default value is `false`, `true` to encapsulate all strings with `"`, `false` to leave them unquoted)* |
| csv\_exclude\_col | string | Comma delimited list of column names to ignore in CSV output *(optional, by default all columns are included)* |
| csv\_set\_delimiter | string | Character that will be used as column delimiter in CSV output *(optional, default value is `;`)* |
| csv\_set\_dec\_mark | string | Character that will be used as decimal separator in CSV output *(optional, default value is `.`)* |
| csv\_set\_timeformat | string | Format for datetime type in CSV output or `unix` for unix timestamp *(optional, default value is `yyyy-MM-ddTHH:mm:ss.fffffffZ`)* |
| csv\_set\_newline | string | New line type *(optional, default value is `unix`, possible values `win`, `mac`, `unix`)* |

### Excel / G-Sheets[​](/market-data/rest-api/#excel--g-sheets "Direct link to Excel / G-Sheets")

There are several ways to use data from our REST API inside the Excel, Google Sheets, or similar calculation sheet application. This section will do as best as possible to keep all information up to date on how you could load the data into these applications. Feel free to contact support if we are missing an option.

#### CSV download, import:[​](/market-data/rest-api/#csv-download-import "Direct link to CSV download, import:")

1. Open the data in the CSV format from the browser eg. `https://rest.coinapi.io/v1/exchangerate/USD?apikey=YOUR_API_KEY&invert=true&output_format=csv`
2. Save the data to the file with the .csv extension.
3. Use the file saved and import it into the software.
4. When configuring import, refer to the parameters like delimiter from the [Output data format](/market-data/rest-api/#output-data-format)

The platform-independent way described above is based on CSV but could also be used in other formats like JSON and XML as long as the software support it, but the import procedure needs to be adjusted accordingly.

#### Microsoft Excel[​](/market-data/rest-api/#microsoft-excel "Direct link to Microsoft Excel")

* Use [PowerQuery](https://docs.microsoft.com/en-us/power-query/power-query-what-is-power-query) to load the URL directly into the CSV import without saving the file locally.
* Use the [=WEBSERVICE](https://support.office.com/en-us/article/webservice-function-0546a35a-ecc6-4739-aed7-c0b7ce1562c4) function to load the API response directly into the sheet, but this will not parse the data; additional processing is required.

#### Google Sheets[​](/market-data/rest-api/#google-sheets "Direct link to Google Sheets")

* Use [=IMPORT](https://support.google.com/docs/answer/3093335?hl=en) function to load the REST API endpoint and automatically parse the CSV format data into the cells. eg. `=IMPORTDATA("https://rest.coinapi.io/v1/exchangerate/USD?apikey=YOUR_API_KEY&invert=true&output_format=csv`

#### OpenOffice Calc[​](/market-data/rest-api/#openoffice-calc "Direct link to OpenOffice Calc")

* Select the menu Insert -> Sheet From File, 2. In the Insert dialog, put the URL eg. `https://rest.coinapi.io/v1/exchangerate/USD?apikey=YOUR_API_KEY&invert=true&output_format=csv` in the File Name box at the bottom. Set the drop-down list next to that to Web Page Query and click Open. The Text Import dialog opens where you can change the defaults if needed.

Authentication[​](/market-data/rest-api/#authentication "Direct link to Authentication")
----------------------------------------------------------------------------------------

* API Key: ApiKey

CoinApi API key needed to access the endpoints

|  |  |
| --- | --- |
| Security Scheme Type: | apiKey |
| Header parameter name: | X-CoinAPI-Key |

### Contact

COINAPI LTD: [[email protected]](/cdn-cgi/l/email-protection#b9caccc9c9d6cbcdf9dad6d0d7d8c9d097d0d6)

URL: [https://www.coinapi.io](/cdn-cgi/l/email-protection#147c606064672e3b3b6363633a777b7d7a75647d3a7d7b)

### License

[MIT License](https://github.com/api-bricks/api-bricks-sdk/blob/master/LICENSE)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Metric ID per Exchange](/market-data/metadata-tables/metric_id)[Next

Exchange Rates](/market-data/rest-api/exchange-rates/)

* [OpenAPI Specification](/market-data/rest-api/#openapi-specification)
* [Endpoints](/market-data/rest-api/#endpoints)
* [General](/market-data/rest-api/#general)
  + [HTTP Requests](/market-data/rest-api/#http-requests)
  + [Output data format](/market-data/rest-api/#output-data-format)
  + [Excel / G-Sheets](/market-data/rest-api/#excel--g-sheets)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.