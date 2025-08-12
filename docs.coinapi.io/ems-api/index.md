EMS - Starter Guide | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/)

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

* [EMS API](/ems-api/)
* [Authentication](/ems-api/authentication)
* [API limits and billing](/ems-api/api-limits-and-billing-metrics)
* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* EMS API

On this page

EMS - Starter Guide
===================

This section will provide general information about the **Execution Management System API** (`EMS API`) software product and enumerate a number of features that it provides.

info

The keywords "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

What is EMS API?[​](/ems-api/#what-is-ems-api "Direct link to What is EMS API?")
--------------------------------------------------------------------------------

Execution Management System (EMS) is a software that manages orders, executions, and exposure in an efficient, fast, cost-effective, and straightforward manner. An EMS allows you to route orders to multiple cryptocurrency exchanges simultaneously using a simple, robust, and unified Application Programming Interface (API).

The software is provided as a Managed Cloud service - Everything is managed on our side. Hosted in the Cloud by CoinAPI. You manage the deployment using the REST API.

Architecture and components[​](/ems-api/#architecture-and-components "Direct link to Architecture and components")
------------------------------------------------------------------------------------------------------------------

EMS consists of several components listed and ordered by dependency relationship:

1. `Exchange` - Order destination, exchange, or broker.
2. `CoinAPI EMS Edge` - Software that's responsible for communicating with the single specific order destination for which is deployed. This component exposes the `EMS API` for diagnostics purposes which functions visibility are limited to this single destination.
3. `CoinAPI EMS API` - Software that's responsible for exposing fully functional the `EMS API`, maintaining the connection with all instances of `CoinAPI EMS Edge`.
4. `Customer Application` - Customer software using the `EMS API` exposed by the `CoinAPI EMS API` component.

Benefits and features[​](/ems-api/#benefits-and-features "Direct link to Benefits and features")
------------------------------------------------------------------------------------------------

### Low latency support[​](/ems-api/#low-latency-support "Direct link to Low latency support")

Specific projects usually involve High-Frequency Trading (HFT) or Market Making (MM) requiring low latency access to the order destination. `EMS API` was designed to have native support for this kind of activity.

Our Managed Cloud service optimizes the deployment of components to ensure the lowest possible latency for each order destination.

### Normalized API abstraction[​](/ems-api/#normalized-api-abstraction "Direct link to Normalized API abstraction")

Our EMS API provides an abstraction layer that consolidates all supported third-party APIs into a single set of simple and robust data models and protocols. The Exchanges and the Assets are standardized using the Market Data REST API with which this product is compatible. More information about the exchanges and asset standardization can be found in the [Documentation of the Market Data Product](/market-data).

### Industry-standard protocols[​](/ems-api/#industry-standard-protocols "Direct link to Industry-standard protocols")

Our API's can be accessed using multiple protocols widely adopted by the industry as a standard:

* REST
* WebSocket
* FIX 4.4, 5.0
* FIXT 1.1

### Security & Privacy[​](/ems-api/#security--privacy "Direct link to Security & Privacy")

We manage the infrastructure with industry-standard security practices. Your order flow and execution reports are handled with utmost care and privacy.

tip

The software complies with the "SOC 2" and "ISO/IEC 27001 information security certifications.

### Multi-account support[​](/ems-api/#multi-account-support "Direct link to Multi-account support")

Manage an unlimited number of exchange accounts in the cluster (for example, on behalf of your customers).

### SDK and samples for 40+ languages[​](/ems-api/#sdk-and-samples-for-40-languages "Direct link to SDK and samples for 40+ languages")

We have the SDK libraries and code samples available for more than 40+ languages. The full list is available here: <https://github.com/api-bricks/api-bricks-sdk/tree/master>

### Comprehensive support[​](/ems-api/#comprehensive-support "Direct link to Comprehensive support")

Leverage support for all market types and order types.

### High-quality integrations[​](/ems-api/#high-quality-integrations "Direct link to High-quality integrations")

Our integrations with third-party APIs are heavily tested and crafted with stability and latency in mind. For several third parties, we usually use multiple protocols simultaneously or tricks to acquire valuable pieces of information faster.

### Enterprise-grade support and maintenance[​](/ems-api/#enterprise-grade-support-and-maintenance "Direct link to Enterprise-grade support and maintenance")

EMS product is fully supported and maintained to stay ahead of the curve. This approach offloads the often disliked responsibilities of the Software and DevOps Engineers in the organization and enables them to focus on the core business.

### High availability[​](/ems-api/#high-availability "Direct link to High availability")

The EMS software is designed and deployed to ensure high availability. We manage multiple instances of `CoinAPI EMS Edge` and `CoinAPI EMS API` components across different availability zones or cloud providers to ensure continuous service.

### P&L and asset monitoring[​](/ems-api/#pl-and-asset-monitoring "Direct link to P&L and asset monitoring")

Using the EMS, your organization can manage exposure and positions in real-time across all supported order destinations and build sophisticated risk management controls.

Order lifecycle
---------------

This section will describe the lifecycle of the order in the `EMS` software.

Order status description[​](/ems-api/#order-status-description "Direct link to Order status description")
---------------------------------------------------------------------------------------------------------

This table describes how to interpret a specific order status.

| Name | Can transit to | Status description |
| --- | --- | --- |
| `RECEIVED` | `REJECTED` `ROUTING` | The order is processed by the `EMS`. |
| `ROUTING` | `ROUTED` | The order is (on the wire) between the `EMS` and the `Exchange`. |
| `ROUTED` | `REJECTED` `NEW` `PARTIALLY_FILLED` `FILLED` `CANCELED` | The order has been sent to the exchange and not yet active in the order book. |
| `NEW` | `PARTIALLY_FILLED` `FILLED` `PENDING_CANCEL` `CANCELED` | The order is active in the book in its original state. |
| `PENDING_CANCEL` | `NEW` `PARTIALLY_FILLED` `FILLED` `CANCELED` | The order cancelation message has been sent to the `Order destination`. |
| `PARTIALLY_FILLED` | `FILLED` `PENDING_CANCEL` `CANCELED` | The order is partially filled and active in the order book. |
| `FILLED` |  | The order is filled and removed from the order book. This state is terminal. |
| `CANCELED` |  | The order is canceled and removed from the order book. This state is terminal. |
| `REJECTED` |  | The order is rejected. This state is terminal. |

Order status lifecycle[​](/ems-api/#order-status-lifecycle "Direct link to Order status lifecycle")
---------------------------------------------------------------------------------------------------

This table describes how to interpret transitions between order statuses and their initial values.

| Source Status | Destination status | Description |
| --- | --- | --- |
|  | `RECEIVED` | `EMS` received a new order via the API. |
|  | `NEW` | `EMS` received an unseen new order from the `Order destination`. The order was relayed to the destination outside the `EMS`. |
|  | `PARTIALLY_FILLED` | `EMS` received unseen partially filled order from the `Order destination`. The order was relayed to the destination outside the `EMS`. |
| `RECEIVED` | `REJECTED` | `EMS` rejected the order. |
| `RECEIVED` | `ROUTING` | `EMS` delivering the order to the `Order destination`. |
| `ROUTING` | `ROUTED` | `EMS` sent the order to the `Order destination`. |
| `ROUTED` | `REJECTED` | `EMS` received a message from the exchange that the order was rejected. |
| `ROUTED` | `NEW` | `EMS` received a message from the exchange that the order is active in the book in its original state. |
| `ROUTED` | `PARTIALLY_FILLED` | `EMS` received a message from the exchange that part of the order was executed aggressively (removed liquidity). The remaining passive part is active in the book. |
| `ROUTED` | `FILLED` | `EMS` received a message from the exchange that the order was executed aggressively (removed liquidity). |
| `ROUTED` | `CANCELED` | `EMS` received a message from the exchange that the order is in the canceled state. The order has not been in the book as the conditions for the entry were not satisfied. |
| `NEW` | `PARTIALLY_FILLED` | `EMS` received a message from the exchange that part of the passive order was filled. |
| `NEW` | `FILLED` | `EMS` received a message from the exchange that the passive order is filled. |
| `NEW` | `PENDING_CANCEL` | `EMS` received cancel request for the order and successfully relayed it to the `Order destination`. |
| `NEW` | `CANCELED` | `EMS` received a message from the exchange that the passive order was canceled. |
| `PARTIALLY_FILLED` | `FILLED` | `EMS` received a message from the exchange that the remaining part of the passive order is filled. |
| `PARTIALLY_FILLED` | `PENDING_CANCEL` | `EMS` received cancel request for the remaining part of the passive order and successfully relayed it to the `Order destination`. |
| `PARTIALLY_FILLED` | `CANCELED` | `EMS` received a message from the exchange that the remaining part of the passive order is canceled. |
| `PENDING_CANCEL` | `NEW` | `EMS` received a message from the exchange that updated the order before processing the cancellation request or the order cancellation request was rejected. |
| `PENDING_CANCEL` | `PARTIALLY_FILLED` | `EMS` received a message from the exchange that updated the order before processing the cancellation request or the order cancellation request was rejected. |
| `PENDING_CANCEL` | `FILLED` | `EMS` received a message from the exchange that updated the order before processing the cancellation request or the order cancellation request was rejected. |
| `PENDING_CANCEL` | `CANCELED` | `EMS` received a message from exchange` that updated the order before processing the cancellation request or the order cancellation request was rejected. |

Order parameters
----------------

This section will describe parameters of the order in the `EMS` sofware.

### Order type

`EMS` supports only the `LIMIT` order type. Market orders don't have price protection, and because of that, they are not supported. As an alternative, you can use the Immediate or Cancel `IOC` order and provide the worst execution price to achieve the same result.

### Time in force

Time in force is a special instruction used when placing a trade to indicate how long an order will remain active before it expires.

The table below describes how to interpret time in force parameter values.

| Time in force | Shortcode | Description |
| --- | --- | --- |
| `GOOD_TILL_CANCEL` | `GTC` | A Good Till Cancel (GTC) is a default type of time-in-force. The order that lasts until is completed or canceled. |
| `GOOD_TILL_TIME_EXCHANGE` | `GTTE` | The Good Till Time Exchange (GTTE) time in force lets you set an expiration date and time up until which an order will be active in the book. The exchange handles the execution of the cancel originated from parameter. |
| `GOOD_TILL_TIME_OEML` | `GTTO` | The Good Till Time OEML (GTTO) time in force lets you set an expiration date and time up until which an order will be active in the book. The `CoinAPI EMS Edge` sending the cancel request originated from the parameter. Worth mentioning that: (a) The cancellation request will not be sent if the software will be not be running at the time of expiration. (b) This parameter does not depend on the exchange. (c) The clock of the server running `CoinAPI EMS Edge` is used to trigger the cancelation request at the expiration. |
| `FILL_OR_KILL` | `FOK` | Fill or kill (FOK) is a type of time in force used to instruct an exchange to execute a transaction immediately and completely or not at all. This order will only remove liquidity from the order book. It must be filled in its entirety or canceled (killed). |
| `IMMEDIATE_OR_CANCEL` | `IOC` | An immediate or cancel order (IOC) is a type of time in force used to instruct an exchange to execute all or part immediately and cancels any unfilled portion of the order. This order will only remove liquidity from the order book. It will fill whatever part of the order it can immediately and cancel any remaining amount so that no part of the order is added to the order book. |

The table below displays a breakdown of the `EMS` support of specific time in force values by the `Order destination`.

| Order destination id | `GTC` | `GTTE` | `GTTO` | `FOK` | `IOC` |
| --- | --- | --- | --- | --- | --- |
| BINANCE | X |  | X | X | X |
| BINANCEUAT | X |  | X | X | X |
| BINANCEJE | X |  | X | X | X |
| BINANCEUS | X |  | X | X | X |
| BINANCEFTS | X |  | X | X | X |
| BINANCEFTSUAT | X |  | X | X | X |
| BINANCEFTSC | X |  | X | X | X |
| BINANCEFTSCUAT | X |  | X | X | X |
| BINANCEOPTV | X |  | X | X | X |
| BINANCEOPTVUAT | X |  | X | X | X |
| BITFINEX | X | X | X | X | X |
| BITMEX | X |  | X | X | X |
| BITMEXUAT | X |  | X | X | X |
| BITSTAMP | X |  | X | X | X |
| BLOCKCHAINEXCHANGE | X | X | X |  | X |
| COINBASE | X |  | X | X | X |
| GEMINI | X |  | X | X | X |
| HITBTC | X | X | X | X | X |
| KRAKEN | X |  | X |  | X |
| KRAKENFTS | X |  | X |  | X |
| POLONIEX | X |  | X | X | X |
| LMAXDIGITAL | X |  | X | X | X |
| LMAXDIGITALUAT | X |  | X | X | X |
| DERIBIT | X |  | X | X | X |
| DERIBITUAT | X |  | X | X | X |
| DYDX | X | X | X | X | X |

Legend: `X` - supported.

### Execution instructions

Execution instruction puts restrictions on order handling at the matching engine. More than one instruction can apply to an order. The table below describes how to interpret execution instructions parameter values. Legend: `X` - supported.

| Instruction | Shortcode | Description |
| --- | --- | --- |
| `AUCTION_ONLY` | `AO` | An Auction Only (AO) instructs exchange that this order is for the auction only book for the next auction. The order may be cancelled up until the the auction locks, after which cancel requests will be rejected. |
| `INDICATION_OF_INTEREST` | `IOI` | An indication of interest (IOI) instructs exchange that this order should be processed as request for liquidity from block trading market markets. |
| `MAKER_OR_CANCEL` | `MOC` | A Maker or cancel (MOC) instructs exchange that this order will only add liquidity to the order book. If any part of the order could be filled immediately, the whole order will instead be rejected before any execution occurs. This instruction is also known as `Post only` or `Participate don't initiate`. |
| `CANCEL_ON_DISCONNECT` | `COD` | Cancel on System Failure (Cancel on disconnect) |
| `DO_NOT_CANCEL_ON_DISCONNECT` | `NCOD` | Reinstate on System Failure (Do not cancel on disconnect) |
| `DO_NOT_INCREASE` | `DNI` | (Reduce only) If part of a position is closed by any other means than the reduce-only order, the reduce-only order will be automatically adjusted downwards. If the trader decides to increase their position before the reduce-only order is executed, the quantity of the reduce-only order will not increase as well. |

The table below displays a breakdown of the `EMS` support of specific execution instructions by the `Order destination`.

| Order destination id | `MOC` | `AO` | `IOI` | `COD` | `NCOD` | `DNI` |
| --- | --- | --- | --- | --- | --- | --- |
| `BINANCE` | X |  |  |  |  |  |
| `BINANCEUAT` | X |  |  |  |  |  |
| `BINANCEJE` | X |  |  |  |  |  |
| `BINANCEUS` | X |  |  |  |  |  |
| `BINANCEFTS` | X |  |  |  |  |  |
| `BINANCEFTSUAT` | X |  |  |  |  |  |
| `BINANCEFTSC` | X |  |  |  |  |  |
| `BINANCEFTSCUAT` | X |  |  |  |  |  |
| `BINANCEOPTV` | X |  |  |  |  |  |
| `BINANCEOPTVUAT` | X |  |  |  |  |  |
| `BITFINEX` | X |  |  |  |  |  |
| `BITMEX` | X |  |  |  |  |  |
| `BITMEXUAT` | X |  |  |  |  |  |
| `BITSTAMP` |  |  |  |  |  |  |
| `BLOCKCHAINEXCHANGE` | X |  |  |  |  |  |
| `COINBASE` | X |  |  |  |  |  |
| `GEMINI` | X | X | X |  |  |  |
| `HITBTC` |  |  |  |  |  |  |
| `KRAKENFTS` | X |  |  |  |  |  |
| `KRAKEN` | X |  |  |  |  |  |
| `POLONIEX` | X |  |  |  |  |  |
| `LMAXDIGITAL` |  |  |  | X | X |  |
| `LMAXDIGITALUAT` |  |  |  | X | X |  |
| `DERIBIT` | X |  |  |  |  | X |
| `DERIBITUAT` | X |  |  |  |  | X |
| `DYDX` | X |  |  |  |  | X |

Legend: `X` - supported.

Market Orders[​](/ems-api/#market-orders "Direct link to Market Orders")
------------------------------------------------------------------------

While our API inherently supports limit orders, we understand the necessity for some clients to operate with market orders. This documentation provides a technical solution for simulating market orders using our limit order functionality with the **Fill or Kill (FOK)** option.

### Technical Solution[​](/ems-api/#technical-solution "Direct link to Technical Solution")

To mimic the behavior of a market order using our API, which inherently supports limit orders, clients can place a limit order with a **Fill or Kill (FOK)** condition. This approach effectively replicates the immediate execution characteristic of a market order while requiring the specification of a maximum (for buy orders) or minimum (for sell orders) price limit.

**Implementation Steps**:

1. **Prepare the Order**:

Define the order as a limit order.
Set the price limit to the maximum price the client is willing to pay for a buy order or the minimum price they are willing to accept for a sell order.
Ensure that the order quantity meets the client's requirement for the transaction.

2. **Set the FOK Condition**:

Apply the Fill or Kill condition to the order. This condition mandates that the order must be executed immediately in its entirety or not executed at all. It ensures that partial fills do not occur, closely aligning with the nature of a market order.

3. **Execution and Validation**:

Upon submission, the EMS will attempt to fill the order immediately based on the specified price limits and the **FOK** condition.
If the order cannot be filled immediately and completely within the defined price range, it will be automatically cancelled, ensuring no partial fills.

### Advantages and Considerations[​](/ems-api/#advantages-and-considerations "Direct link to Advantages and Considerations")

* **Immediate Execution**: The **FOK** condition ensures that the order, if executed, is filled immediately, mirroring the behavior of a market order.
* **Price Control**: Clients maintain control over the maximum or minimum price limits, adding a layer of price protection that standard market orders do not provide.
* **Simplicity**: This method avoids the need for additional development or integration, utilizing the existing infrastructure of our API.

Using a limit order API can be considered simpler and more straightforward for several reasons, especially when compared to other types of trading orders. Here are some factors that contribute to the perceived simplicity:

**Predictability and Control**:

* **Price Certainty**: Limit orders allow users to specify the maximum or minimum price at which they are willing to buy or sell an asset. This provides certainty about the price, which is not the case with market orders, where the execution price can vary.
* **Control over Execution**: Users have better control over their trades. They can decide not to execute a trade if the market does not reach their specified price, avoiding unwanted entries or exits in volatile market conditions.
* **Consistent behaviour**: Not all the order destinations support market orders or when they support it, usually they are implmeneted in form of limit orders.

**Straightforward Implementation**:

* **Simplicity in API Design**: Limit order APIs are generally straightforward to implement and integrate because the parameters are clear and well-defined (quantity, price, and sometimes duration).
* **Fewer Real-time Considerations**: Unlike market orders, where getting the best available price in real-time is crucial, limit orders are placed based on predefined criteria. This can reduce the complexity associated with rapid decision-making and real-time data processing.

**Reduced Need for Immediate Market Data**:

* **Less Dependency on Real-time Pricing**: Since the execution of a limit order is based on the user's specified price, there's less need for immediate or real-time market data, unlike market orders where knowing the current market price is crucial for order execution.

**Cost Predictability**:

* **Avoidance of Slippage**: With limit orders, the risk of slippage (the difference between the expected price of a trade and the price at which the trade is executed) is eliminated. Users can be more confident about the cost of their trades, making financial planning and risk management more straightforward.

**Ease of Monitoring and Management**:

* **Set and Forget**: Users can place limit orders and not worry about monitoring the market constantly. The order will only execute if the market price meets the user's criteria, making it a more passive form of trading.
* **Batch Processing Friendly**: For applications or trading strategies that place numerous orders, limit orders can be more manageable as they don't require immediate processing or constant monitoring of market prices.

**Reduced Impact on Market Price**:

* **Minimized Market Disruption**: Limit orders can be less disruptive to the market price, especially for large orders. They are executed only at the user's specified price, avoiding large, sudden impacts on the market price that can occur with large market orders.

In summary, a limit order API can offer a simpler and more controlled trading experience, with price certainty, reduced need for real-time market data, straightforward implementation, and predictable costs. These factors contribute to its appeal, especially for users or systems focusing on strategic, planned trading activities rather than immediate, real-time market engagement.

Time[​](/ems-api/#time "Direct link to Time")
---------------------------------------------

For all input and output time values ISO 8601 standard is used.

| Format specifier | Description |
| --- | --- |
| `yyyy` | The year as a four-digit number. |
| `MM` | The month, from 01 through 12. |
| `dd` | The day of the month, from 01 through 31. |
| `HH` | The hour, using a 24-hour clock from 00 to 23. |
| `mm` | The minute, from 00 through 59. |
| `ss` | The second, from 00 through 59. |
| `fff` | The milliseconds in a date and time value. |
| `fffffff` | The ten millionths of a second in a date and time value. |

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

When time zone information is not supplied, we will assume the UTC time zone.

Output time values are formatted using the following patterns:

1. `yyyy-MM-ddTHH:mm:ss.fffffffZ`
2. `yyyy-MM-dd`

info

All time values we provide are UTC time zone. Do not assume otherwise.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Next

Authentication](/ems-api/authentication)

* [What is EMS API?](/ems-api/#what-is-ems-api)
* [Architecture and components](/ems-api/#architecture-and-components)
* [Benefits and features](/ems-api/#benefits-and-features)
  + [Low latency support](/ems-api/#low-latency-support)
  + [Normalized API abstraction](/ems-api/#normalized-api-abstraction)
  + [Industry-standard protocols](/ems-api/#industry-standard-protocols)
  + [Security & Privacy](/ems-api/#security--privacy)
  + [Multi-account support](/ems-api/#multi-account-support)
  + [SDK and samples for 40+ languages](/ems-api/#sdk-and-samples-for-40-languages)
  + [Comprehensive support](/ems-api/#comprehensive-support)
  + [High-quality integrations](/ems-api/#high-quality-integrations)
  + [Enterprise-grade support and maintenance](/ems-api/#enterprise-grade-support-and-maintenance)
  + [High availability](/ems-api/#high-availability)
  + [P&L and asset monitoring](/ems-api/#pl-and-asset-monitoring)
* [Order status description](/ems-api/#order-status-description)
* [Order status lifecycle](/ems-api/#order-status-lifecycle)
* [Market Orders](/ems-api/#market-orders)
  + [Technical Solution](/ems-api/#technical-solution)
  + [Advantages and Considerations](/ems-api/#advantages-and-considerations)
* [Time](/ems-api/#time)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.