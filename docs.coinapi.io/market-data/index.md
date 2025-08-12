Market Data API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/)

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
* [Performance Testing Guide](/market-data/performance-testing-guide)

* Market Data API

On this page

Market Data - Starter Guide
===========================

Welcome to the CoinAPI developer documentation.
This document should contain all the information required to properly implement applications using our API.

Overview of the APIs[​](/market-data/#overview-of-the-apis "Direct link to Overview of the APIs")
-------------------------------------------------------------------------------------------------

3 main interfaces can be used to access CoinAPI:

| API | Data | Communication | Description |
| --- | --- | --- | --- |
| RESTful | Live and Historical | Request-response | Stateless API provides the widest range of data, not capable of streaming, only pooling. |
| WebSocket V1 | Live | Publish-subscribe | Stateful API providing streaming of real-time market data. Using a single connection, clients are able to subscribe to multiple data sources. |
| WebSocket DS | Live | Publish-subscribe | **Newly introduced**, stateful API providing streaming of real-time market data with direct connections to each data source for optimized performance and reliability. |
| FIX | Live | Publish-subscribe | Stateful API providing streaming of real-time market data, widely adopted by the finance industry. Using single connection client is able to subscribe to multiple data sources. |

Comparison: REST vs. Streaming Protocols (WebSocket & FIX)[​](/market-data/#comparison-rest-vs-streaming-protocols-websocket--fix "Direct link to Comparison: REST vs. Streaming Protocols (WebSocket & FIX)")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Understanding the differences between REST and streaming protocols like WebSocket and FIX is essential for developers when designing and implementing financial applications. Here's a detailed comparison to guide your choice.

| Feature | REST API | WebSocket & FIX |
| --- | --- | --- |
| **Communication Model** | Request-response model, where the client sends a request and the server responds | Continuous, bidirectional communication allowing for real-time data streaming |
| **Use Case** | Ideal for operations that do not require real-time updates, such as retrieving historical data | Suited for applications requiring real-time market data updates and trading operations |
| **Complexity** | Generally simpler to implement due to the stateless nature of HTTP requests | More complex due to the need for handling continuous connections and real-time data management |
| **Data Freshness** | Data is only as fresh as the last request made by the client | Data is continuously updated in real-time, providing the latest market information |
| **Scalability** | Can be more easily scaled using standard web infrastructure | Scaling requires careful management of connection resources and data throughput |
| **Latency** | Higher latency due to the overhead of making HTTP requests | Lower latency, optimized for real-time data delivery and trading activities |
| **State Management** | Stateless, with each request being independent | Stateful, maintaining a continuous connection state |

### Key Takeaways[​](/market-data/#key-takeaways "Direct link to Key Takeaways")

* **REST API** is straightforward and effective for operations that can tolerate the latency inherent in the request-response model. It's widely used for accessing historical data, account management, and other non-time-sensitive operations.
* **WebSocket & FIX** are tailored for real-time applications, such as live market data feeds, trading platforms, and other scenarios where immediate data access is crucial. They offer lower latency and continuous data streams but come with added complexity in implementation and resource management.

Choosing between REST and streaming protocols depends on your application's specific needs regarding data freshness, real-time updates, and the complexity you're prepared to manage.

Comparison: WebSocket APIs vs. FIX API[​](/market-data/#comparison-websocket-apis-vs-fix-api "Direct link to Comparison: WebSocket APIs vs. FIX API")
-----------------------------------------------------------------------------------------------------------------------------------------------------

Understanding the differences between WebSocket APIs (both V1 and DS) and the FIX API is crucial for developers and financial institutions looking to integrate real-time market data and trading capabilities. Here's a detailed comparison to guide your choice.

| Feature | WebSocket APIs | FIX API |
| --- | --- | --- |
| **Protocol Nature** | Publish-subscribe model, designed for real-time data streaming | Session-based protocol, widely used for trading and order management |
| **Use Case** | Best suited for applications requiring real-time market data updates | Primarily used for trading, order submission, and execution reports |
| **Complexity** | Relatively simple to implement and use | More complex due to its extensive use in trading operations |
| **Data Types** | Primarily focused on market data (quotes, trades, book data) | Supports a wide range of financial information including order entries, executions, and market data |
| **Latency** | Low latency, especially with WebSocket DS API optimized for high-frequency data | Generally low latency, with performance depending on the implementation and network infrastructure |
| **Reliability** | High reliability with TCP-based delivery ensuring message order and integrity | Extremely high reliability and considered the industry standard for trading activities |
| **Authorization** | HTTP based authorization methods | Uses session-based logins with possible additional security measures |
| **Flexibility** | High flexibility in subscribing to specific data types and exchanges | High degree of customization and control over trading operations and data exchange |

### Key Takeaways[​](/market-data/#key-takeaways-1 "Direct link to Key Takeaways")

* **WebSocket APIs** are ideal for applications that require efficient, real-time access to market data. They offer simplicity in implementation and flexibility in data subscription, making them suitable for a wide range of applications beyond trading, such as analytics and monitoring tools.
* **FIX API** is the go-to protocol for trading operations, offering robustness, reliability, and a wide range of functionalities tailored to the needs of traders and financial institutions. Its complexity and capabilities make it the standard for order management and execution in the financial industry.

Choosing between WebSocket APIs and the FIX API depends on your specific requirements, whether you're focusing on real-time data streaming for various applications or engaging in complex trading operations.

Comparison: WebSocket V1 vs. WebSocket DS API[​](/market-data/#comparison-websocket-v1-vs-websocket-ds-api "Direct link to Comparison: WebSocket V1 vs. WebSocket DS API")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

When choosing between WebSocket V1 and WebSocket DS API, it's important to understand their key differences and how they cater to different needs. Here's a comparison to help you decide which API suits your project requirements better.

| Feature | WebSocket V1 API | WebSocket DS API |
| --- | --- | --- |
| **Connection Type** | Possible to acquire the data from multiple data sources using single connection | Separate data sources need separate connection |
| **Routing** | GeoDNS for regional routing to nearest infrastructure | Optimized DNS for more direct connection per specific data source |
| **Data types** | trade, quote, orderbooks, ohlcv, exchange rates, metadata | trade, quote, orderbooks |
| **Authorization** | In protocol authorization, query-string, URL path, header, or JWT | query-string, URL path, header, or JWT |
| **Symbol Filtering** | Flexible symbol filtering | Requires precise symbol identifiers for improved data accuracy |
| **Symbology** | CoinAPI Symbol identifiers | CoinAPI or Exchange symbols identifiers |

### Key Takeaways[​](/market-data/#key-takeaways-2 "Direct link to Key Takeaways")

* **WebSocket V1** is versatile and user-friendly, making it suitable for a wide range of applications that require real-time market data.
* **WebSocket DS API** is tailored for scenarios demanding high data volumes and low latency, such as high-frequency trading platforms. Its direct routing and exchange-specific connections provide a more efficient data stream with reduced latency.

Choosing the right API depends on your specific needs regarding data volume, latency sensitivity, and the complexity of your data subscription requirements. Both APIs continue to be supported, ensuring that you can select the one that best fits your project's needs.

SDK[​](/market-data/#sdk "Direct link to SDK")
----------------------------------------------

Our Software Development Kit (SDK) is available on GitHub at <https://github.com/api-bricks/api-bricks-sdk>.
If possible then we are strongly recommending using our tested libraries available on GitHub, rather than creating new ones.
However, if you decide to create your implementation or to change the existing one, then we encourage you to create a Pull Request to our main repository with the proposed changes,
we will able to include your code in our official repository for use by other users, effectively creating collaboration.

In the repository, you can find libraries or examples for languages or environments like:

* Python
* R
* Matlab
* C#
* C++
* .NET
* Java
* Ruby
* Go
* JavaScript
* TypeScript
* Node.js
* PHP
* Haskell
* Objective-C
* Swift

Security[​](/market-data/#security "Direct link to Security")
-------------------------------------------------------------

The use of encryption is optional, and the decision to use it is on you. On the encrypted endpoints, we are using protocols that are considered the best security practices.

tip

You should assume that we are always providing certificates signed by the Trusted Certification Authority.

Standards and conventions[​](/market-data/#standards-and-conventions "Direct link to Standards and conventions")
----------------------------------------------------------------------------------------------------------------

This section represents used standards and conventions across all documents and API's.

info

The keywords "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

### Variables naming[​](/market-data/#variables-naming "Direct link to Variables naming")

All variables are named using the Snake case (or `snake_case`) naming convention.
This means that words are separated by a single underscore `_` character, no spaces are used, and letters are lowercase.

### Asset codes[​](/market-data/#asset-codes "Direct link to Asset codes")

ISO 4217 currency code standard is used for fiat money identifications.
Cryptocurrency assets are identified using codes used by the general public or adopted by the majority of exchanges.

### Exchange codes[​](/market-data/#exchange-codes "Direct link to Exchange codes")

Exchange on our platform is identified by the specific exchange API and the matching engine behind it. When the example exchange has multiple separate APIs, e.g., for different products SPOT, OPTIONS, or to cover other regions, we will expose these symbols from these respective APIs on different exchange identifiers. Below are examples of BINANCE (multiple APIs, multiple regions) and DERIBIT (single API, single region). A full [listing of exchanges](/market-data/rest-api/metadata/#list-all-exchanges-get) can be queried using the Market Data REST API.

| BINANCE Exchange IDs | Website | Description |
| --- | --- | --- |
| BINANCE | <https://www.binance.com/> | Binance |
| BINANCEDEX | <https://www.binance.org/> | Binance DEX |
| BINANCEFTS | <https://www.binance.com/> | Binance USD-M Futures (USDT/fapi) |
| BINANCEFTSC | <https://www.binance.com/> | Binance COIN-M Futures (Coin/dapi) |
| BINANCEFTSCUAT | <https://www.binance.com/> | Binance Futures Testnet (Coin/dapi) |
| BINANCEFTSUAT | <https://www.binance.com/> | Binance Futures Testnet (USDT/fapi) |
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

### Numbers precision[​](/market-data/#numbers-precision "Direct link to Numbers precision")

Numbers in our platform can have a maximum of 19 digits overall, but no more than 9 decimal places. In cases when the number represents aggregate value then we allow 38 digits overall, but still no more than 9 decimal places.

### Time[​](/market-data/#time "Direct link to Time")

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

Authentication](/market-data/authentication)

* [Overview of the APIs](/market-data/#overview-of-the-apis)
* [Comparison: REST vs. Streaming Protocols (WebSocket & FIX)](/market-data/#comparison-rest-vs-streaming-protocols-websocket--fix)
  + [Key Takeaways](/market-data/#key-takeaways)
* [Comparison: WebSocket APIs vs. FIX API](/market-data/#comparison-websocket-apis-vs-fix-api)
  + [Key Takeaways](/market-data/#key-takeaways-1)
* [Comparison: WebSocket V1 vs. WebSocket DS API](/market-data/#comparison-websocket-v1-vs-websocket-ds-api)
  + [Key Takeaways](/market-data/#key-takeaways-2)
* [SDK](/market-data/#sdk)
* [Security](/market-data/#security)
* [Standards and conventions](/market-data/#standards-and-conventions)
  + [Variables naming](/market-data/#variables-naming)
  + [Asset codes](/market-data/#asset-codes)
  + [Exchange codes](/market-data/#exchange-codes)
  + [Numbers precision](/market-data/#numbers-precision)
  + [Time](/market-data/#time)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.