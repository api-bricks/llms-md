Exchange Rates API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/exchange-rates-api/)

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

* [Exchange Rates API](/exchange-rates-api/)
* [Authentication](/exchange-rates-api/authentication)
* [Realtime REST API](/exchange-rates-api/rest-api-realtime/exchange-rates-realtime-rest-api)
* [Historical REST API](/exchange-rates-api/rest-api-historical/exchange-rates-historical-rest-api)
* [Websocket API](/exchange-rates-api/websocket/)
* [JSON RPC](/exchange-rates-api/jsonrpc-api)
* [How-to guides](/exchange-rates-api/how-to-guides/)

* Exchange Rates API

On this page

Exchange Rates - Starter Guide
==============================

Welcome to the CoinAPI developer documentation.
This document should contain all the information required to properly implement applications using our API.

Overview of the APIs[​](/exchange-rates-api/#overview-of-the-apis "Direct link to Overview of the APIs")
--------------------------------------------------------------------------------------------------------

3 main interfaces can be used to access CoinAPI:

| API | Data | Communication | Description |
| --- | --- | --- | --- |
| RESTful | Live and Historical | Request-response | Stateless API provides the widest range of data, not capable of streaming, only pooling. |
| WebSocket | Live | Publish-subscribe | Stateful API providing streaming of real-time market data. Using a single connection, clients are able to subscribe to multiple data streams. |

Comparison: REST vs. Streaming Protocols (WebSocket)[​](/exchange-rates-api/#comparison-rest-vs-streaming-protocols-websocket "Direct link to Comparison: REST vs. Streaming Protocols (WebSocket)")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Understanding the differences between REST and streaming protocols like WebSocket is essential for developers when designing and implementing financial applications. Here's a detailed comparison to guide your choice.

| Feature | REST API | WebSocket |
| --- | --- | --- |
| **Communication Model** | Request-response model, where the client sends a request and the server responds | Continuous, bidirectional communication allowing for real-time data streaming |
| **Use Case** | Ideal for operations that do not require real-time updates, such as retrieving historical data | Suited for applications requiring real-time market data updates |
| **Complexity** | Generally simpler to implement due to the stateless nature of HTTP requests | More complex due to the need for handling continuous connections and real-time data management |
| **Data Freshness** | Data is only as fresh as the last request made by the client | Data is continuously updated in real-time, providing the latest market information |
| **Scalability** | Can be more easily scaled using standard web infrastructure | Scaling requires careful management of connection resources and data throughput |
| **Latency** | Higher latency due to the overhead of making HTTP requests | Lower latency, optimized for real-time data delivery |
| **State Management** | Stateless, with each request being independent | Stateful, maintaining a continuous connection state |

### Key Takeaways[​](/exchange-rates-api/#key-takeaways "Direct link to Key Takeaways")

* **REST API** is straightforward and effective for operations that can tolerate the latency inherent in the request-response model. It's widely used for accessing historical data, account management, and other non-time-sensitive operations.
* **WebSocket** is tailored for real-time applications, such as live market data feeds, trading platforms, and other scenarios where immediate data access is crucial. It offers lower latency and continuous data streams but comes with added complexity in implementation and resource management.

Choosing between REST and streaming protocols depends on your application's specific needs regarding data freshness, real-time updates, and the complexity you're prepared to manage.

SDK[​](/exchange-rates-api/#sdk "Direct link to SDK")
-----------------------------------------------------

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

Security[​](/exchange-rates-api/#security "Direct link to Security")
--------------------------------------------------------------------

The use of encryption is optional, and the decision to use it is on you. On the encrypted endpoints, we are using protocols that are considered the best security practices.

tip

You should assume that we are always providing certificates signed by the Trusted Certification Authority.

Standards and conventions[​](/exchange-rates-api/#standards-and-conventions "Direct link to Standards and conventions")
-----------------------------------------------------------------------------------------------------------------------

This section represents used standards and conventions across all documents and API's.

info

The keywords "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

### Variables naming[​](/exchange-rates-api/#variables-naming "Direct link to Variables naming")

All variables are named using the Snake case (or `snake_case`) naming convention.
This means that words are separated by a single underscore `_` character, no spaces are used, and letters are lowercase.

### Asset codes[​](/exchange-rates-api/#asset-codes "Direct link to Asset codes")

ISO 4217 currency code standard is used for fiat money identifications.
Cryptocurrency assets are identified using codes used by the general public or adopted by the majority of exchanges.

### Numbers precision[​](/exchange-rates-api/#numbers-precision "Direct link to Numbers precision")

Numbers in our platform can have a maximum of 19 digits overall, but no more than 9 decimal places. In cases when the number represents aggregate value then we allow 38 digits overall, but still no more than 9 decimal places.

### Time[​](/exchange-rates-api/#time "Direct link to Time")

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

Authentication](/exchange-rates-api/authentication)

* [Overview of the APIs](/exchange-rates-api/#overview-of-the-apis)
* [Comparison: REST vs. Streaming Protocols (WebSocket)](/exchange-rates-api/#comparison-rest-vs-streaming-protocols-websocket)
  + [Key Takeaways](/exchange-rates-api/#key-takeaways)
* [SDK](/exchange-rates-api/#sdk)
* [Security](/exchange-rates-api/#security)
* [Standards and conventions](/exchange-rates-api/#standards-and-conventions)
  + [Variables naming](/exchange-rates-api/#variables-naming)
  + [Asset codes](/exchange-rates-api/#asset-codes)
  + [Numbers precision](/exchange-rates-api/#numbers-precision)
  + [Time](/exchange-rates-api/#time)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.