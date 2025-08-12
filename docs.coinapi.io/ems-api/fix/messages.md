Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/fix/messages)

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

  + [Introduction](/ems-api/fix/)
  + [Messages](/ems-api/fix/messages)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [FIX API](/ems-api/fix/)
* Messages

On this page

Messages
========

This section will provide necessary documentation for the FIX protocol messages.

New Order Single 35=D[​](/ems-api/fix/messages#new-order-single-35d "Direct link to new-order-single-35d")
----------------------------------------------------------------------------------------------------------

| FIX Field Name | WebSocket Field Name | Description |
| --- | --- | --- |
| `ClOrdID` | `client_order_id` | The unique identifier of the order assigned by the client. |
| `ClOrdLinkID` | `client_order_id` | The same value as for `ClOrdID`. |
| `ExDestination` | `exchange_id` | Exchange identifier used to identify the routing destination. |
| `SecurityID` | `symbol_coinapi` or  `symbol_exchange` | CoinAPI or Exchange symbol, depends on the value of `SecurityIDSource <22>` type |
| `SecurityIDSource` | N/A | Identifies source of the `SecurityID <48>` value. `8` = `EXCHANGE`, `101` = `COINAPI` |
| `Symbol` | The same value as for `SecurityID`. |  |
| `TransactTime` | N/A | Time this order request was initiated/released by the trader, trading system, or intermediary. |
| `OrdType` | order\_type | Order types are documented in the separate section: [EMS / Starter Guide / Order parameters / Order type](#ems-order-params-type) |
| `Side` | side | Side of order. |
| `Price` | price | Order price. |
| `OrderQty` | amount\_order | Order quantity. |
| `TimeInForce` | time\_in\_force | Order time in force options are documented in the separate section: [EMS / Starter Guide / Order parameters / Time in force](#ems-order-params-tif) |
| `ExpireTime` | expire\_time | Expiration time. Conditionaly required if `TimeInForce <59>` = `GTD` |
| `ExecInst` | `exec_inst` | Order execution instructions are documented in the separate section: [EMS / Starter Guide / Order parameters / Execution instructions](#ems-order-params-exec) |

Order Cancel Request 35=F[​](/ems-api/fix/messages#order-cancel-request-35f "Direct link to order-cancel-request-35f")
----------------------------------------------------------------------------------------------------------------------

| FIX Field Name | WebSocket Field Name | Description |
| --- | --- | --- |
| `ClOrdID` | N/A | Unique ID of cancel request as assigned by the client. |
| `OrigClOrdID` | `client_order_id` | The unique identifier of the order assigned by the client. One of the properties (`OrigClOrdID`, `OrderID`) is required to identify the order. |
| `OrderID` | `exchange_order_id` | Unique identifier of the order assigned by the exchange or executing system. One of the properties (`OrigClOrdID`, `OrderID`) is required to identify the order. |
| `SecurityExchange` | `exchange_id` | Exchange identifier used to identify the routing destination. |
| `TransactTime` | N/A | Time this order request was initiated/released by the trader, trading system, or intermediary. |
| `Side` | N/A | This value is ignored. |
| `Symbol` | N/A | This value is ignored. |

Order Mass Cancel Request 35=q[​](/ems-api/fix/messages#order-mass-cancel-request-35q "Direct link to order-mass-cancel-request-35q")
-------------------------------------------------------------------------------------------------------------------------------------

| FIX Field Name | WebSocket Field Name | Description |
| --- | --- | --- |
| `ClOrdID` | N/A | Unique ID of `Order Mass Cancel Request <q>` as assigned by the client. |
| `MassCancelRequestType` | N/A | `7` = Cancel all orders |
| `SecurityExchange` | `exchange_id` | Exchange identifier used to identify routing destination. |

Execution Report 35=8[​](/ems-api/fix/messages#execution-report-358 "Direct link to execution-report-358")
----------------------------------------------------------------------------------------------------------

| FIX Field Name | WebSocket Field Name | Description |
| --- | --- | --- |
| `OrderID` | `client_order_id` | Unique identifier of the order as assigned by client. |
| `SecondaryOrderID` | `exchange_order_id` | Unique identifier of the order assigned by the exchange or executing system. |
| `ExecID` | N/A | Unique identifier of execution message as assigned by sell-side. |
| `ExecType` | N/A | `I` = Order Status. Describes the purpose of the execution report. |
| `OrdStatus` | `status` | Order statuses and the lifecycle are documented in the separate section: [EMS / Starter Guide / Order Lifecycle](#ems-order-lifecycle) |
| `SecurityID` | `symbol_coinapi` or  `symbol_exchange` | CoinAPI or Exchange symbol, depends on the value of `SecurityIDSource <22>` type |
| `SecurityIDSource` | N/A | Identifies source of the `SecurityID <48>` value. `8` = `EXCHANGE`, `101` = `COINAPI` |
| `Symbol` | The same value as for `SecurityID`. |  |
| `SecurityExchange` | `exchange_id` | Exchange identifier used to identify the routing destination. |
| `Side` | `side` | Side of order. |
| `OrderQty` | `amount_order` | Quantity ordered. |
| `CumQty` | `amount_filled` | Total quantity filled. |
| `LeavesQty` | `amount_open` | Quantity open for further execution. `LeavesQty <151>` = `OrderQty <38>` - `CumQty <14>`. |

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/ems-api/fix/)[Next

SOR - WebSocket API](/ems-api/sor-websocket-api)

* [New Order Single 35=D](/ems-api/fix/messages#new-order-single-35d)
* [Order Cancel Request 35=F](/ems-api/fix/messages#order-cancel-request-35f)
* [Order Mass Cancel Request 35=q](/ems-api/fix/messages#order-mass-cancel-request-35q)
* [Execution Report 35=8](/ems-api/fix/messages#execution-report-358)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.