Flat Files - Overview | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/)

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

* Flat Files

On this page

Flat Files - Overview
=====================

Welcome to the CoinAPI Flat Files documentation. This API provides access to historical cryptocurrency market data in flat file format, allowing for efficient retrieval and analysis of large datasets.

What is the Flat Files?[​](/flat-files-api/#what-is-the-flat-files "Direct link to What is the Flat Files?")
------------------------------------------------------------------------------------------------------------

The Flat Files is a powerful tool for accessing comprehensive historical market data. It currently offers access via an S3-compatible API, allowing you to use familiar S3 operations and tools to retrieve data.

### Available Data Types[​](/flat-files-api/#available-data-types "Direct link to Available Data Types")

Our Flat Files provides access to the following types of data:

1. **Quotes**: Best bid and ask prices with associated volumes.
2. **Trades**: Executed trades with price, volume, and direction.
3. **Limit Book Data**: Full order book snapshots and updates.

Comming soon:

1. **OHLCV Data**: Open, High, Low, Close, and Volume data for various time periods.

### Current and Future Access Methods[​](/flat-files-api/#current-and-future-access-methods "Direct link to Current and Future Access Methods")

Currently, we offer a pull-based S3 API for accessing flat files. This allows you to retrieve data on-demand using S3-compatible tools and libraries.

**Coming Soon: Push API**

We're excited to announce that we'll soon be releasing a Push API feature. With this new capability, you'll be able to:

* Define specific data sets you need
* Have data automatically pushed to your designated S3 bucket on a daily basis
* Streamline your data pipeline by receiving updates without manual polling

Stay tuned for more information about this upcoming feature!

Getting Started[​](/flat-files-api/#getting-started "Direct link to Getting Started")
-------------------------------------------------------------------------------------

To start using the Flat Files:

1. Sign up for a CoinAPI account if you haven't already.
2. Obtain your API credentials from the dashboard.
3. Choose an S3-compatible client or SDK.
4. Configure your client with our endpoint and your credentials.
5. Start retrieving historical market data!

**NOTE: To access flat files, you need to add usage credits to your account via the Customer Portal (Billing → Add Usage Credits). Once you have sufficient balance in your account, you can start listing and downloading the files as explained in the documentation.**

For detailed information on authentication, billing, and API usage, please refer to the articles from the menu.

Standards and conventions[​](/flat-files-api/#standards-and-conventions "Direct link to Standards and conventions")
-------------------------------------------------------------------------------------------------------------------

This section represents used standards and conventions across all documents and API's.

info

The keywords "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

### Variables naming[​](/flat-files-api/#variables-naming "Direct link to Variables naming")

All variables are named using the Snake case (or `snake_case`) naming convention.
This means that words are separated by a single underscore `_` character, no spaces are used, and letters are lowercase.

### Asset codes[​](/flat-files-api/#asset-codes "Direct link to Asset codes")

ISO 4217 currency code standard is used for fiat money identifications.
Cryptocurrency assets are identified using codes used by the general public or adopted by the majority of exchanges.

### Exchange codes[​](/flat-files-api/#exchange-codes "Direct link to Exchange codes")

Exchange on our platform is identified by the specific exchange API and the matching engine behind it. When the example exchange has multiple separate APIs, e.g., for different products SPOT, OPTIONS, or to cover other regions, we will expose these symbols from these respective APIs on different exchange identifiers. Below are examples of BINANCE (multiple APIs, multiple regions) and DERIBIT (single API, single region). A full [listing of exchanges](/market-data/rest-api/metadata/#list-all-exchanges-get) can be queried using the Market Data REST API.

| BINANCE Exchange IDs | Website | Description |
| --- | --- | --- |
| BINANCE | <https://www.binance.com/> | Binance |
| BINANCEDEX | <https://www.binance.org/> | Binance DEX |
| BINANCEFTS | <https://www.binance.com/> | Binance Futures (USDT/dapi) |
| BINANCEFTSC | <https://www.binance.com/> | Binance Futures (Coin/fapi) |
| BINANCEFTSCUAT | <https://www.binance.com/> | Binance Futures Testnet (Coin/fapi) |
| BINANCEFTSUAT | <https://www.binance.com/> | Binance Futures Testnet (USDT/dapi) |
| BINANCEJE | <https://www.binance.je/> | Binance Jersey |
| BINANCEJEX | <https://www.jex.com/en> | Binance JEX |
| BINANCEKR | <https://www.binance.kr/> | Binance Korea |
| BINANCEOPTV | <https://www.binance.com/> | Binance Options Vanilla (vapi) |
| BINANCEOPTVUAT | <https://www.binance.com/> | Binance Options Vanilla Testnet (vapi) |
| BINANCEUAT | <https://www.binance.com/> | Binance Testnet |
| BINANCEUG | <https://www.binance.co.ug/> | Binance Uganda |
| BINANCEUS | <https://www.binance.us/> | Binance US |

| DERIBIT Exchange IDs | Website | Description |
| --- | --- | --- |
| DERIBIT | <https://www.deribit.com/> | Deribit |

### Numbers precision[​](/flat-files-api/#numbers-precision "Direct link to Numbers precision")

Numbers in our platform can have a maximum of 19 digits overall, but no more than 9 decimal places. In cases when the number represents aggregate value then we allow 38 digits overall, but still no more than 9 decimal places.

### Time[​](/flat-files-api/#time "Direct link to Time")

For all input and output time values ISO 8601 standard is used.

| Format specifier | Description |
| --- | --- |
| `yyyy` | The year is a four-digit number. |
| `MM` | The month, from 01 through 12. |
| `dd` | The day of the month, from 01 through 31. |
| `HH` | The hour, using a 24-hour clock from 00 to 23. |
| `mm` | The minute, from 00 through 59. |
| `ss` | The second, from 00 through 59. |
| `fff` | The milliseconds in a date and time value. |
| `fffffff` | The ten-millionths of a second in a date and time value. |

Input time values are parsed using the following formats as far as possible:

* `yyyy-MM-ddTHH:mm:ss.fffffff`
* `yyyy-MM-ddTHH:mm:ss.fff`
* `yyyy-MM-ddTHH:mm:ss`
* `yyyy-MM-ddTHH:mm`
* `yyyy-MM-ddTHH`
* `yyyy-MM-dd`
* `yyyyMMddTHHmmssfffffff`
* `yyyyMMddTHHmmssfff`
* `yyyyMMddTHHmmss`
* `yyyyMMddTHHmm`
* `yyyyMMddTHH`
* `yyyyMMdd`

info

When time zone information is not supplied, we will assume the UTC zone.

Output time values are formatted using the following patterns:

1. `yyyy-MM-ddTHH:mm:ss.fffffffZ`
2. `yyyy-MM-dd`

info

All time values we provide are UTC zones. Do not assume otherwise.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Next

Data Types and File Structure Overview](/flat-files-api/data-types/)

* [What is the Flat Files?](/flat-files-api/#what-is-the-flat-files)
  + [Available Data Types](/flat-files-api/#available-data-types)
  + [Current and Future Access Methods](/flat-files-api/#current-and-future-access-methods)
* [Getting Started](/flat-files-api/#getting-started)
* [Standards and conventions](/flat-files-api/#standards-and-conventions)
  + [Variables naming](/flat-files-api/#variables-naming)
  + [Asset codes](/flat-files-api/#asset-codes)
  + [Exchange codes](/flat-files-api/#exchange-codes)
  + [Numbers precision](/flat-files-api/#numbers-precision)
  + [Time](/flat-files-api/#time)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.