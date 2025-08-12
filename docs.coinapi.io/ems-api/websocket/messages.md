Messages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/websocket/messages)

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

  + [Introduction](/ems-api/websocket/)
  + [Messages](/ems-api/websocket/messages)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* [WebSocket API](/ems-api/websocket/)
* Messages

On this page

Messages
========

This section will provide necessary documentation for the WebSocket protocol messages.

The message type is identified by the `type` property of the JSON object. This document is organized into sections, each per specific message `type`.

| Message `type` | Trigger | Description |
| --- | --- | --- |
| `SERVER_INFO` | On connection open Every `1 second` On update | Heartbeat and server information. |
| `ORDER_NEW_SINGLE_REQUEST` | On new order | Submit new order. |
| `ORDER_CANCEL_SINGLE_REQUEST` | On order cancel | Cancel single order. |
| `ORDER_CANCEL_ALL_REQUEST` | On order cancel | Cancel all orders. |
| `ORDER_EXEC_REPORT_SNAPSHOT` | On connection open | Snapshot of all order execution reports. |
| `ORDER_EXEC_REPORT_UPDATE` | On update | Update of the order execution report. |
| `BALANCE_SNAPSHOT` | On connection open | Snapshot of all balances. |
| `BALANCE_UPDATE` | On update | Update of the balance. |
| `POSITION_SNAPSHOT` | On connection open | Snapshot of all positions. |
| `POSITION_UPDATE` | On update | Update of the position. |
| `SYMBOLS_SNAPSHOT` | On connection open | Snapshot of markets symbols. |
| `MESSAGE_REJECT` | On order placing/cancelling rejection. | Text message. |

SERVER\_INFO IN[​](/ems-api/websocket/messages#server_info-in "Direct link to server_info-in")
----------------------------------------------------------------------------------------------

> Example of the `SERVER_INFO` message.

```
{  
	"type": "SERVER_INFO",  
	"time": "2020-02-07T12:37:46.6967101Z",  
	"instance_guid": "16bab28c-8c7c-4af7-815b-923ea8ecbf4a",  
	"exchange_id": "BINANCEJE",  
	"server_version": "1.3521",  
	"server_name": "HDC2-ENC-06-BAY-05",  
	"dns_name": "HDC2-ENC-06-BAY-05.us-east-1.corpintra.net",  
	"is_running": true,  
	"time_server_start": "2020-02-07T10:25:22.3022141Z"  
}
```

This message is used internally to measure the real-time latency of the link and acts as a heartbeat.

Delivery triggers:

* On connection open
* Every `1 second`
* On update

### Properties[​](/ems-api/websocket/messages#properties "Direct link to Properties")

| Name | Type | Description |
| --- | --- | --- |
| type | string | Message type, constant `SERVER_INFO`. |
| time | datetime | Time message sent time to measure the link latency. |
| instance\_guid | string | The server process randomly generated GUID. It will change on each software restart. |
| exchange\_id | string | Exchange identifier. |
| server\_version | string | Server software version. |
| server\_name | string | Server name. |
| dns\_name | string | DNS name. |
| is\_running | boolean | Is the server on the other side running? Update with the `false` value will be sent before the shutdown. |
| time\_server\_start | datetime | Time of server software start. |

ORDER\_NEW\_SINGLE\_REQUEST OUT[​](/ems-api/websocket/messages#order_new_single_request-out "Direct link to order_new_single_request-out")
------------------------------------------------------------------------------------------------------------------------------------------

> Example of the `ORDER_NEW_SINGLE_REQUEST` message creating order on the `KRAKEN` exchange by the `symbol_id_exchange`.

```
{  
  "type": "ORDER_NEW_SINGLE_REQUEST",  
  "exchange_id": "KRAKEN",  
  "client_order_id": "6ab36bc1-344d-432e-ac6d-0bf44ee64c2b",  
  "symbol_id_exchange": "XBT/USDT",  
  "amount_order": 0.045,  
  "price": 0.0783,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": "2020-01-01T10:45:20.1677709Z",  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

> Another example of the `ORDER_NEW_SINGLE_REQUEST` message creating order on the same market by the `symbol_id_coinapi`.

```
{  
  "type": "ORDER_NEW_SINGLE_REQUEST",  
  "exchange_id": "KRAKEN",  
  "client_order_id": "6ab36bc1-344d-432e-ac6d-0bf44ee64c2b",  
  "symbol_id_coinapi": "KRAKEN_SPOT_BTC_USDT",  
  "amount_order": 0.045,  
  "price": 0.0783,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": "2020-01-01T10:45:20.1677709Z",  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

This message is used to send a new order to the exchange.

### Properties[​](/ems-api/websocket/messages#properties-1 "Direct link to Properties")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `ORDER_NEW_SINGLE_REQUEST`. |
| exchange\_id | string | true | Exchange identifier. |
| client\_order\_id | string | true | The unique identifier of the order assigned by the client. |
| symbol\_id\_exchange | string | false | Exchange symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order. |
| symbol\_id\_coinapi | string | false | CoinAPI symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order. |
| amount\_order | number | true | Order quantity. |
| price | number | true | Order price. |
| side | string | true | Side of order. Allowed values: `BUY` or `SELL`. |
| order\_type | string | true | Order types are documented in the separate section: [EMS / Starter Guide / Order parameters / Order type](#ems-order-params-type) |
| time\_in\_force | string | true | Order time in force options are documented in the separate section: [EMS / Starter Guide / Order parameters / Time in force](#ems-order-params-tif) |
| expire\_time | date | false | Expiration time. Conditionaly required for orders with time\_in\_force = `GOOD_TILL_TIME_EXCHANGE` or `GOOD_TILL_TIME_OEML`. |
| exec\_inst | [string] | false | Order execution instructions are documented in the separate section: [EMS / Starter Guide / Order parameters / Execution instructions](#ems-order-params-exec) |

ORDER\_CANCEL\_SINGLE\_REQUEST OUT[​](/ems-api/websocket/messages#order_cancel_single_request-out "Direct link to order_cancel_single_request-out")
---------------------------------------------------------------------------------------------------------------------------------------------------

> Example of the `ORDER_CANCEL_SINGLE_REQUEST` message to cancel a single order identified by the `exchange_order_id` on the `BITSTAMP` exchange.

```
{  
  "type": "ORDER_CANCEL_SINGLE_REQUEST",  
  "exchange_id": "BITSTAMP",  
  "exchange_order_id": "1234567"  
}
```

> Another example of the `ORDER_CANCEL_SINGLE_REQUEST` message to cancel a single order identified by the `client_order_id` on the `BITSTAMP` exchange.

```
{  
  "type": "ORDER_CANCEL_SINGLE_REQUEST",  
  "exchange_id": "BITSTAMP",  
  "client_order_id": "d8574207d9e3b16a4a5511753eeef1751"  
}
```

Request cancel for an existing order. The order can be canceled using the `client_order_id` or `exchange_order_id`.

### Properties[​](/ems-api/websocket/messages#properties-2 "Direct link to Properties")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `ORDER_CANCEL_SINGLE_REQUEST`. |
| exchange\_id | string | true | Exchange identifier. |
| exchange\_order\_id | string | false | Unique identifier of the order assigned by the exchange or executing system. One of the properties (`exchange_order_id`, `client_order_id`) is required to identify the order. |
| client\_order\_id | string | false | The unique identifier of the order assigned by the client. One of the properties (`exchange_order_id`, `client_order_id`) is required to identify the order. |

ORDER\_CANCEL\_ALL\_REQUEST OUT[​](/ems-api/websocket/messages#order_cancel_all_request-out "Direct link to order_cancel_all_request-out")
------------------------------------------------------------------------------------------------------------------------------------------

> Example of the `ORDER_CANCEL_ALL_REQUEST` message to cancel all open orders on the `KRAKEN` exchange.

```
{  
    "type": "ORDER_CANCEL_ALL_REQUEST",  
    "exchange_id": "KRAKEN"  
}
```

This request cancels all open orders on a single specified exchange.

### Properties[​](/ems-api/websocket/messages#properties-3 "Direct link to Properties")

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `ORDER_CANCEL_ALL_REQUEST`. |
| exchange\_id | body | string | true |

ORDER\_EXEC\_REPORT\_SNAPSHOT IN[​](/ems-api/websocket/messages#order_exec_report_snapshot-in "Direct link to order_exec_report_snapshot-in")
---------------------------------------------------------------------------------------------------------------------------------------------

> Example of the `ORDER_EXEC_REPORT_SNAPSHOT` message delivering all open orders from the KRAKEN exchange.

```
{  
	"type": "ORDER_EXEC_REPORT_SNAPSHOT",  
	"exchange_id": "KRAKEN",  
	"data":   
	[  
		{  
			"exchange_id": "KRAKEN",  
			"client_order_id": "KPP-222389382-AQ",  
			"exchange_order_id": "90832ASASAS89789-1112",  
			"symbol_id_exchange": "XBT/USDT",  
			"symbol_id_coinapi": "KRAKEN_SPOT_BTC_USDT",  
			"amount_order": 0.045,  
			"amount_filled": 0,  
			"amount_open": 0.22,  
			"status": "NEW",  
			"price": 0.0783,  
			"avg_px": 0.0783,  
			"side": "BUY",  
			"order_type": "LIMIT",  
			"time_in_force": "GOOD_TILL_CANCEL",  
			"expire_time": "2020-01-01T10:45:20.1677709Z",  
			"exec_inst": "MAKER_OR_CANCEL"  
			"status_history": [  
				[  
					"RECEIVED",  
					"2020-05-27T11:16:20.1677709Z"  
				],  
				[  
					"ROUTING",  
					"2020-05-27T11:16:20.1677710Z"  
				],  
				[  
					"ROUTED",  
					"2020-05-27T11:16:20.1677800Z"  
				],  
				[  
					"NEW",  
					"2020-05-27T11:16:20.1677951Z"  
				]  
			],  
			"fills": [  
				{  
					"time": "2020-01-01T10:45:20.1677709Z",  
  					"price": 10799.2,  
  					"amount": 0.002  
				}  
			]  
		}  
	]  
}
```

This message provides all open orders from the single exchange and will be sent separately for all interconnected exchanges.

When this message is received, then the client must discard all open orders from this exchange and apply the snapshot, which later will be modified by the `ORDER_EXEC_REPORT_UPDATE` messages.

Delivery triggers:

* On connection open

### Properties[​](/ems-api/websocket/messages#properties-4 "Direct link to Properties")

| Parameter | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| type | string | true | Message type, constant `ORDER_EXEC_REPORT_SNAPSHOT`. |  |
| data | array | object | true | No description |
| » exchange\_id | body | string | true | Exchange identifier used to identify the routing destination. |
| » client\_order\_id | body | string | true | The unique identifier of the order assigned by the client. |
| » client\_order\_id\_format\_exchange | body | string | true | The unique identifier of the order assigned by the client converted to the exchange order tag format for the purpose of tracking it. |
| » exchange\_order\_id | body | string | true | Unique identifier of the order assigned by the exchange or executing system. |
| » symbol\_id\_exchange | body | string | false | Exchange symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order. |
| » symbol\_id\_coinapi | body | string | false | CoinAPI symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order. |
| » amount\_order | body | number | true | Order quantity. |
| » amount\_filled | body | number | true | Total quantity filled. |
| » amount\_open | body | number | true | Quantity open for further execution. `amount_open` = `amount_order` - `amount_filled` |
| » status | body | string | true | Order statuses and the lifecycle are documented in the separate section: [EMS / Starter Guide / Order Lifecycle](#ems-order-lifecycle) |
| » status\_history | body | array | true | Timestamped history of order status changes. |
| » price | body | number | true | Order price. |
| » avg\_px | body | number | true | Calculated average price of all fills on this order. |
| » side | body | string | true | Side of order. |
| » order\_type | body | string | true | Order types are documented in the separate section: [EMS / Starter Guide / Order parameters / Order type](#ems-order-params-type) |
| » time\_in\_force | body | string | true | Order time in force options are documented in the separate section: [EMS / Starter Guide / Order parameters / Time in force](#ems-order-params-tif) |
| » expire\_time | body | date | false | Expiration time. Conditionaly required for orders with time\_in\_force = `GOOD_TILL_TIME_EXCHANGE` or `GOOD_TILL_TIME_OEML`. |
| » exec\_inst | body | [string] | false | Order execution instructions are documented in the separate section: [EMS / Starter Guide / Order parameters / Execution instructions](#ems-order-params-exec) |
| » error\_message | body | number | true | Error message |
| » fills | body | array | true | Relay fill information on working orders |

### Enumerated Values[​](/ems-api/websocket/messages#enumerated-values "Direct link to Enumerated Values")

| Parameter | Value |
| --- | --- |
| » side | BUY |
| » side | SELL |
| » order\_type | LIMIT |
| » time\_in\_force | GOOD\_TILL\_CANCEL |
| » time\_in\_force | GOOD\_TILL\_TIME\_EXCHANGE |
| » time\_in\_force | GOOD\_TILL\_TIME\_OMS |
| » time\_in\_force | FILL\_OR\_KILL |
| » time\_in\_force | IMMEDIATE\_OR\_CANCEL |
| » exec\_inst | MAKER\_OR\_CANCEL |
| » exec\_inst | AUCTION\_ONLY |
| » exec\_inst | INDICATION\_OF\_INTEREST |

ORDER\_EXEC\_REPORT\_UPDATE IN[​](/ems-api/websocket/messages#order_exec_report_update-in "Direct link to order_exec_report_update-in")
---------------------------------------------------------------------------------------------------------------------------------------

> Example of the `ORDER_EXEC_REPORT_UPDATE` message notifying that an execution report for the order is changed. In this case, one order changed status, and it's filled.

```
{  
	"exchange_id": "KRAKEN",  
	"client_order_id": "KPP-222389382-AQ",  
	"client_order_id_format_exchange": "f81211e2-27c4-b86a-8143-01088ba9222c",  
	"exchange_order_id": "90832ASASAS89789-1112",  
	"symbol_id_exchange": "XBT/USDT",  
	"symbol_id_coinapi": "KRAKEN_SPOT_BTC_USDT",  
	"amount_order": 0.045,  
	"amount_open": 0,  
	"amount_filled": 0.045,  
	"status": "FILLED",  
	"price": 0.0783,  
	"avg_px": 0.0783,  
	"side": "BUY",  
	"order_type": "LIMIT",  
	"time_in_force": "GOOD_TILL_CANCEL",  
	"expire_time": "2020-01-01T10:45:20.1677709Z",  
	"exec_inst": "MAKER_OR_CANCEL"  
	"status_history": [  
		[  
			"RECEIVED",  
			"2020-05-27T11:16:20.1677709Z"  
		],  
		[  
			"ROUTING",  
			"2020-05-27T11:16:20.1677710Z"  
		],  
		[  
			"ROUTED",  
			"2020-05-27T11:16:20.1677800Z"  
		],  
		[  
			"NEW",  
			"2020-05-27T11:16:20.1677951Z"  
		],  
		[  
			"FILLED",  
			"2020-05-27T11:16:30.6456457Z"  
		]  
	],  
	"fills": [  
		{  
			"time": "2020-01-01T10:45:20.1677709Z",  
			"price": 10799.2,  
			"amount": 0.002  
		}  
	]	  
}
```

This message is sent to notify the client that the order execution report changed.

When this message is received, then the client must update the execution report in the memory to maintain the current state of execution reports for all open orders.

The initial state of the collection is delivered via the snapshot message `ORDER_EXEC_REPORT_SNAPSHOT`.

Delivery triggers:

* On execution report update

### Properties[​](/ems-api/websocket/messages#properties-5 "Direct link to Properties")

| Parameter | In | Type | Required | Description |
| --- | --- | --- | --- | --- |
| type | string | true | Message type, constant `ORDER_EXEC_REPORT_UPDATE`. |  |
| exchange\_id | body | string | true | Exchange identifier used to identify the routing destination. |
| client\_order\_id | body | string | true | The unique identifier of the order assigned by the client. |
| client\_order\_id\_format\_exchange | body | string | true | The unique identifier of the order assigned by the client converted to the exchange order tag format for the purpose of tracking it. |
| exchange\_order\_id | body | string | true | Unique identifier of the order assigned by the exchange or executing system. |
| symbol\_id\_exchange | body | string | false | Exchange symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order. |
| symbol\_id\_coinapi | body | string | false | CoinAPI symbol. One of the properties (`symbol_id_exchange`, `symbol_id_coinapi`) is required to identify the market for the new order. |
| amount\_order | body | number | true | Order quantity. |
| amount\_filled | body | number | true | Total quantity filled. |
| amount\_open | body | number | true | Quantity open for further execution. `amount_open` = `amount_order` - `amount_filled` |
| status | body | string | true | Order statuses and the lifecycle are documented in the separate section: [EMS / Starter Guide / Order Lifecycle](#ems-order-lifecycle) |
| status\_history | body | array | true | Timestamped history of order status changes. |
| price | body | number | true | Order price. |
| avg\_px | body | number | false | Calculated average price of all fills on this order. |
| side | body | string | true | Side of order. |
| order\_type | body | string | true | Order types are documented in the separate section: [EMS / Starter Guide / Order parameters / Order type](#ems-order-params-type) |
| time\_in\_force | body | string | true | Order time in force options are documented in the separate section: [EMS / Starter Guide / Order parameters / Time in force](#ems-order-params-tif) |
| expire\_time | body | date | false | Expiration time. Conditionaly required for orders with time\_in\_force = `GOOD_TILL_TIME_EXCHANGE` or `GOOD_TILL_TIME_OEML`. |
| exec\_inst | body | [string] | false | Order execution instructions are documented in the separate section: [EMS / Starter Guide / Order parameters / Execution instructions](#ems-order-params-exec) |
| error\_message | body | number | true | Error message |
| fills | body | array | true | Relay fill information on working orders |

### Enumerated Values[​](/ems-api/websocket/messages#enumerated-values-1 "Direct link to Enumerated Values")

| Parameter | Value |
| --- | --- |
| » side | BUY |
| » side | SELL |
| » order\_type | LIMIT |
| » time\_in\_force | GOOD\_TILL\_CANCEL |
| » time\_in\_force | GOOD\_TILL\_TIME\_EXCHANGE |
| » time\_in\_force | GOOD\_TILL\_TIME\_OMS |
| » time\_in\_force | FILL\_OR\_KILL |
| » time\_in\_force | IMMEDIATE\_OR\_CANCEL |
| » exec\_inst | MAKER\_OR\_CANCEL |
| » exec\_inst | AUCTION\_ONLY |
| » exec\_inst | INDICATION\_OF\_INTEREST |

BALANCE\_SNAPSHOT IN[​](/ems-api/websocket/messages#balance_snapshot-in "Direct link to balance_snapshot-in")
-------------------------------------------------------------------------------------------------------------

> Example of the `BALANCE_SNAPSHOT` message from the `KRAKEN` exchange.

```
{  
    "type": "BALANCE_SNAPSHOT",  
    "exchange_id": "KRAKEN",  
    "data": [  
        {  
			"asset_id_exchange": "XBT",  
			"asset_id_coinapi": "BTC",  
			"balance": 0.00134444,  
			"available": 0.00134444,  
			"locked": 0,  
			"last_updated_by": "EXCHANGE",  
			"rate_usd": 9544.21  
        },  
		{  
			"asset_id_exchange": "BCH",  
			"asset_id_coinapi": "BCHABC",  
			"balance": 1234,  
			"available": 1000,  
			"locked": 234,  
			"last_updated_by": "BALANCE_MANAGER",  
			"rate_usd": 228.12  
        }  
    ]  
}
```

This message provides all balances from the single exchange and will be sent separately for all interconnected exchanges.

When this message is received, then the client must discard all balances from this exchange and apply the snapshot, which later will be modified by the `BALANCE_UPDATE` messages.

Delivery triggers:

* On connection open

### Properties[​](/ems-api/websocket/messages#properties-6 "Direct link to Properties")

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `BALANCE_SNAPSHOT`. |
| exchange\_id | string | false | Exchange identifier. |
| exchange\_id | string | false | Exchange identifier. |
| data | [object] | false | No description |
| » asset\_id\_exchange | string | false | Exchange currency code. |
| » asset\_id\_coinapi | string | false | CoinAPI currency code. |
| » balance | number(float) | false | Value of the current total currency balance on the exchange. |
| » available | number(float) | false | Value of the current available currency balance on the exchange that can be used as collateral. |
| » locked | number(float) | false | Value of the current locked currency balance by the exchange. |
| » last\_updated\_by | string | false | Source of the last modification. |
| » rate\_usd | number(float) | false | Current exchange rate to the USD for the single unit of the currency. |

### Enumerated Values[​](/ems-api/websocket/messages#enumerated-values-2 "Direct link to Enumerated Values")

| Property | Value |
| --- | --- |
| last\_updated\_by | INITIALIZATION |
| last\_updated\_by | BALANCE\_MANAGER |
| last\_updated\_by | EXCHANGE |

BALANCE\_UPDATE IN[​](/ems-api/websocket/messages#balance_update-in "Direct link to balance_update-in")
-------------------------------------------------------------------------------------------------------

> Example of the `BALANCE_UPDATE` message from the `KRAKEN` exchange.

```
{  
    "type": "BALANCE_UPDATE",  
    "exchange_id": "KRAKEN",  
	"asset_id_exchange": "XBT",  
	"asset_id_coinapi": "BTC",  
	"balance": 0.00134444,  
	"available": 0,  
	"locked": 0.00134444,  
	"last_updated_by": "EXCHANGE",  
	"rate_usd": 9544.21  
}
```

This message is sent to notify the client that the balance for the specific exchange currency pair changed.

When this message is received, the client must update the balance in the memory to maintain the current state of balance across all exchanges and currencies.

The initial state of the collection is delivered via the snapshot message `BALANCE_SNAPSHOT`.

Delivery triggers:

* On balance update

### Properties[​](/ems-api/websocket/messages#properties-7 "Direct link to Properties")

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `BALANCE_SNAPSHOT`. |
| exchange\_id | string | false | Exchange identifier. |
| exchange\_id | string | false | Exchange identifier. |
| asset\_id\_exchange | string | false | Exchange currency code. |
| asset\_id\_coinapi | string | false | CoinAPI currency code. |
| balance | number(float) | false | Value of the current total currency balance on the exchange. |
| available | number(float) | false | Value of the current available currency balance on the exchange that can be used as collateral. |
| locked | number(float) | false | Value of the current locked currency balance by the exchange. |
| last\_updated\_by | string | false | Source of the last modification. |
| rate\_usd | number(float) | false | Current exchange rate to the USD for the single unit of the currency. |

### Enumerated Values[​](/ems-api/websocket/messages#enumerated-values-3 "Direct link to Enumerated Values")

| Property | Value |
| --- | --- |
| last\_updated\_by | INITIALIZATION |
| last\_updated\_by | BALANCE\_MANAGER |
| last\_updated\_by | EXCHANGE |

POSITION\_SNAPSHOT IN[​](/ems-api/websocket/messages#position_snapshot-in "Direct link to position_snapshot-in")
----------------------------------------------------------------------------------------------------------------

> Example of the `POSITION_SNAPSHOT` message from the `KRAKENFTS` exchange.

```
{  
	"type": "POSITION_SNAPSHOT",  
	"exchange_id": "KRAKENFTS",  
	"data":   
	[  
		{  
			"symbol_id_exchange": "XBT/USDT",  
			"symbol_id_coinapi": "KRAKENFTS_PERP_BTC_USDT",  
			"avg_entry_price": 0.00134444,  
			"quantity": 0.00134444,  
			"side": "BUY",  
			"unrealised_pnl": 0,  
			"leverage": 0,  
			"cross_margin": true,  
			"liquidation_price": 0.072323  
		}  
	]  
}
```

This message provides all positions from the single exchange and will be sent separately for all interconnected exchanges.

When this message is received, then the client must discard al positions from this exchange and apply the snapshot, which later will be modified by the `POSITION_UPDATE` messages.

Delivery triggers:

* On connection open

### Properties[​](/ems-api/websocket/messages#properties-8 "Direct link to Properties")

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `POSITION_SNAPSHOT`. |
| exchange\_id | string | false | Exchange identifier. |
| data | [object] | false | No description |
| » symbol\_id\_exchange | string | false | Exchange symbol. |
| » symbol\_id\_coinapi | string | false | CoinAPI symbol. |
| » avg\_entry\_price | number | false | Calculated average price of all fills on this position. |
| » quantity | number | false | The current position quantity. |
| » side | string | false | Side of order. |
| » unrealized\_pnl | number | false | Unrealised profit or loss (PNL) of this position. |
| » leverage | number | false | Leverage for this position reported by the exchange. |
| » cross\_margin | boolean | false | Is cross margin mode enable for this position? |
| » liquidation\_price | number | false | Liquidation price. If mark price will reach this value, the position will be liquidated. |

POSITION\_UPDATE IN[​](/ems-api/websocket/messages#position_update-in "Direct link to position_update-in")
----------------------------------------------------------------------------------------------------------

> Example of the `POSITION_UPDATE` message from the `KRAKENFTS` exchange.

```
{  
	"type": "POSITION_UPDATE",  
	"exchange_id": "KRAKENFTS",  
	"symbol_id_exchange": "XBT/USDT",  
	"symbol_id_coinapi": "KRAKENFTS_PERP_BTC_USDT",  
	"avg_entry_price": 0.00134444,  
	"quantity": 0.00134444,  
	"side": "BUY",  
	"unrealised_pnl": 0,  
	"leverage": 0,  
	"cross_margin": true,  
	"liquidation_price": 0.072323  
}
```

This message is sent to notify the client that the position changed.

When this message is received, then the client must update the position in the memory to maintain the current state of all positions across all symbols and exchanges.

The initial state of the collection is delivered via the snapshot message `POSITION_SNPASHOT`.

Delivery triggers:

* On position update

### Properties[​](/ems-api/websocket/messages#properties-9 "Direct link to Properties")

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `POSITION_SNAPSHOT`. |
| exchange\_id | string | false | Exchange identifier. |
| symbol\_id\_exchange | string | false | Exchange symbol. |
| symbol\_id\_coinapi | string | false | CoinAPI symbol. |
| avg\_entry\_price | number | false | Calculated average price of all fills on this position. |
| quantity | number | false | The current position quantity. |
| side | string | false | Side of order. |
| unrealized\_pnl | number | false | Unrealised profit or loss (PNL) of this position. |
| leverage | number | false | Leverage for this position reported by the exchange. |
| cross\_margin | boolean | false | Is cross margin mode enable for this position? |
| liquidation\_price | number | false | Liquidation price. If mark price will reach this value, the position will be liquidated. |

SYMBOLS\_SNAPSHOT IN[​](/ems-api/websocket/messages#symbols_snapshot-in "Direct link to symbols_snapshot-in")
-------------------------------------------------------------------------------------------------------------

> Example of the `SYMBOLS_SNAPSHOT` message.

```
{  
    "type": "SYMBOLS_SNAPSHOT",  
    "exchange_id": "BITMEX",  
    "data": [  
	  {  
		"symbol_id_coinapi": "BITMEX_FTS_ETH_USD_200925",  
		"symbol_id_exchange": "ETHUSDU20",  
		"asset_id_base_exchange": "ETH",  
		"asset_id_quote_exchange": "USD",  
		"asset_id_base_coinapi": "ETH",  
		"asset_id_quote_coinapi": "USD",  
		"price_precision": 0.010000000,  
		"size_precision": 1.000000000  
	  },  
	  {  
		"symbol_id_coinapi": "BITMEX_FTS_LTC_BTC_200925",  
		"symbol_id_exchange": "LTCU20",  
		"asset_id_base_exchange": "LTC",  
		"asset_id_quote_exchange": "XBT",  
		"asset_id_base_coinapi": "LTC",  
		"asset_id_quote_coinapi": "BTC",  
		"price_precision": 0.000001000,  
		"size_precision": 1.000000000  
	  }  
    ]  
}
```

This message provides all market symbols from the single exchange and will be sent separately for all interconnected exchanges.

When this message is received, then the client must discard all market symbols from this exchange and apply the snapshot.

Delivery triggers:

* On connection open

### Properties[​](/ems-api/websocket/messages#properties-10 "Direct link to Properties")

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `SYMBOLS_SNAPSHOT`. |
| exchange\_id | string | false | Exchange identifier. |
| data | [object] | false | No description |
| » symbol\_id\_exchange | string | false | Exchange symbol identifier. |
| » symbol\_id\_coinapi | string | false | CoinAPI symbol identifier. |
| » asset\_id\_base\_exchange | string | false | Base asset exchange identifier. |
| » asset\_id\_quote\_exchange | string | false | Quote asset exchange identifier. |
| » asset\_id\_base\_coinapi | string | false | Base asset CoinAPI identifier. |
| » asset\_id\_quote\_coinapi | string | false | Quote asset CoinAPI identifier. |
| » price\_precision | number | false | Price precision for the symbol. |
| » size\_precision | number | false | Size precision for the symbol. |

MESSAGE\_REJECT IN[​](/ems-api/websocket/messages#message_reject-in "Direct link to message_reject-in")
-------------------------------------------------------------------------------------------------------

> Example of the `MESSAGE_REJECT` object.

```
{  
  "type": "MESSAGE_REJECT",  
  "reject_reason": "ORDER_ID_NOT_FOUND",  
  "exchange_id": "BINANCE",  
  "message": "Order with ID: BINANCE-7d8a-4888 not found",  
  "rejected_message": "{\"client_order_id\":\"BINANCE-7d8a-4888\",\"exchange_id\":\"BINANCE\",\"type\":\"ORDER_CANCEL_SINGLE_REQUEST\"}"  
}
```

Object is used to communicate rejection of user order request.

### Properties[​](/ems-api/websocket/messages#properties-11 "Direct link to Properties")

MessageReject object.

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | Message type, constant `MESSAGE_REJECT`. |
| reject\_reason | string | true | Cause of rejection. Allowed values: `OTHER`, `EXCHANGE_UNREACHABLE`, `EXCHANGE_RESPONSE_TIMEOUT`, `ORDER_ID_NOT_FOUND`, `INVALID_TYPE`, `METHOD_NOT_SUPPORTED`, `JSON_ERROR`, |
| exchange\_id | string | false | If the message related to exchange, then the identifier of the exchange will be provided. |
| message | string | true | Message text. |
| rejected\_message | string | false | Value of rejected request, if available |

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/ems-api/websocket/)[Next

Introduction](/ems-api/fix/)

* [SERVER\_INFO IN](/ems-api/websocket/messages#server_info-in)
  + [Properties](/ems-api/websocket/messages#properties)
* [ORDER\_NEW\_SINGLE\_REQUEST OUT](/ems-api/websocket/messages#order_new_single_request-out)
  + [Properties](/ems-api/websocket/messages#properties-1)
* [ORDER\_CANCEL\_SINGLE\_REQUEST OUT](/ems-api/websocket/messages#order_cancel_single_request-out)
  + [Properties](/ems-api/websocket/messages#properties-2)
* [ORDER\_CANCEL\_ALL\_REQUEST OUT](/ems-api/websocket/messages#order_cancel_all_request-out)
  + [Properties](/ems-api/websocket/messages#properties-3)
* [ORDER\_EXEC\_REPORT\_SNAPSHOT IN](/ems-api/websocket/messages#order_exec_report_snapshot-in)
  + [Properties](/ems-api/websocket/messages#properties-4)
  + [Enumerated Values](/ems-api/websocket/messages#enumerated-values)
* [ORDER\_EXEC\_REPORT\_UPDATE IN](/ems-api/websocket/messages#order_exec_report_update-in)
  + [Properties](/ems-api/websocket/messages#properties-5)
  + [Enumerated Values](/ems-api/websocket/messages#enumerated-values-1)
* [BALANCE\_SNAPSHOT IN](/ems-api/websocket/messages#balance_snapshot-in)
  + [Properties](/ems-api/websocket/messages#properties-6)
  + [Enumerated Values](/ems-api/websocket/messages#enumerated-values-2)
* [BALANCE\_UPDATE IN](/ems-api/websocket/messages#balance_update-in)
  + [Properties](/ems-api/websocket/messages#properties-7)
  + [Enumerated Values](/ems-api/websocket/messages#enumerated-values-3)
* [POSITION\_SNAPSHOT IN](/ems-api/websocket/messages#position_snapshot-in)
  + [Properties](/ems-api/websocket/messages#properties-8)
* [POSITION\_UPDATE IN](/ems-api/websocket/messages#position_update-in)
  + [Properties](/ems-api/websocket/messages#properties-9)
* [SYMBOLS\_SNAPSHOT IN](/ems-api/websocket/messages#symbols_snapshot-in)
  + [Properties](/ems-api/websocket/messages#properties-10)
* [MESSAGE\_REJECT IN](/ems-api/websocket/messages#message_reject-in)
  + [Properties](/ems-api/websocket/messages#properties-11)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.