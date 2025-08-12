List of symbols for the exchange | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/rest-api/list-of-symbols-for-the-exchange)

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

  + [Introduction](/flat-files-api/rest-api/push-api)
  + [Metadata](/flat-files-api/rest-api/metadata)

    - [List all exchanges](/flat-files-api/rest-api/list-all-exchanges)
    - [List all exchanges by exchange\_id](/flat-files-api/rest-api/list-all-exchanges-by-exchange-id)
    - [List all schemas](/flat-files-api/rest-api/list-all-schemas)
    - [List of symbols for the exchange](/flat-files-api/rest-api/list-of-symbols-for-the-exchange)
  + [Data Storage](/flat-files-api/rest-api/data-storage)
  + [Orders](/flat-files-api/rest-api/orders)

* [Push API](/flat-files-api/rest-api/push-api)
* [Metadata](/flat-files-api/rest-api/metadata)
* List of symbols for the exchange

List of symbols for the exchange
================================

```
GET

/api/metadata/symbols/:exchange_id
----------------------------------
```

List of symbols for the exchange

Request[​](/flat-files-api/rest-api/list-of-symbols-for-the-exchange#request "Direct link to Request")
------------------------------------------------------------------------------------------------------

### Path Parameters

**exchange\_id** stringrequired

The ID of the exchange (from the Metadata -> Exchanges)



### Query Parameters

**filter\_symbol\_id** string

The filter for symbol ID.

**filter\_asset\_id** string

The filter for asset ID.

Responses[​](/flat-files-api/rest-api/list-of-symbols-for-the-exchange#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------------

* 200

successful operation

* text/plain
* application/json
* text/json

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol identifier.

**exchange\_id** stringnullable

Gets or sets the exchange identifier.

**symbol\_type** stringnullable

Gets or sets the symbol type.

**asset\_id\_base** stringnullable

Gets or sets the base asset identifier.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset identifier.

**asset\_id\_unit** stringnullable

Gets or sets the unit asset identifier.

**future\_contract\_unit** doublenullable

Gets or sets the contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

Gets or sets the asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

Gets or sets the future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Gets or sets a value indicating whether the option type is a call.

**option\_strike\_price** doublenullable

Gets or sets the strike price for options.

**option\_contract\_unit** doublenullable

Gets or sets the contract unit for options.

**option\_exercise\_style** stringnullable

Gets or sets the exercise style for options.

**option\_expiration\_time** date-timenullable

Gets or sets the expiration time for options.

**contract\_delivery\_time** date-timenullable

Gets or sets the delivery time for contracts.

**contract\_unit** doublenullable

Gets or sets the contract unit for contracts.

**contract\_unit\_asset** stringnullable

Gets or sets the asset used as the unit for contracts.

**contract\_id** stringnullable

Gets or sets the contract identifier.

**contract\_display\_name** stringnullable

Gets or sets the display name of the contract.

**contract\_display\_description** stringnullable

Gets or sets the display description of the contract.

**data\_start** stringnullable

Gets the start date of the data in string format ("yyyy-MM-dd").

**data\_end** stringnullable

Gets the end date of the data in string format ("yyyy-MM-dd").

**data\_quote\_start** date-timenullable

Gets or sets the start date of quote data.

**data\_quote\_end** date-timenullable

Gets or sets the end date of quote data.

**data\_orderbook\_start** date-timenullable

Gets or sets the start date of order book data.

**data\_orderbook\_end** date-timenullable

Gets or sets the end date of order book data.

**data\_trade\_start** date-timenullable

Gets or sets the start date of trade data.

**data\_trade\_end** date-timenullable

Gets or sets the end date of trade data.

**index\_id** stringnullable

Gets or sets the index identifier.

**index\_display\_name** stringnullable

Gets or sets the display name of the index.

**index\_display\_description** stringnullable

Gets or sets the display description of the index.

**symbol\_id\_exchange** stringnullable

Gets or sets the symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

Gets or sets the base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

Gets or sets the quote asset identifier in the exchange.

**price\_precision** doublenullable

Gets or sets the price precision.

**size\_precision** doublenullable

Gets or sets the size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "exchange_id": "string",  
    "symbol_type": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "asset_id_unit": "string",  
    "future_contract_unit": 0,  
    "future_contract_unit_asset": "string",  
    "future_delivery_time": "2025-08-12T06:09:09.085Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:09.085Z",  
    "contract_delivery_time": "2025-08-12T06:09:09.085Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:09.085Z",  
    "data_quote_end": "2025-08-12T06:09:09.085Z",  
    "data_orderbook_start": "2025-08-12T06:09:09.085Z",  
    "data_orderbook_end": "2025-08-12T06:09:09.085Z",  
    "data_trade_start": "2025-08-12T06:09:09.085Z",  
    "data_trade_end": "2025-08-12T06:09:09.085Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0  
  }  
]
```

```
[  
  {  
    "symbol_id": "KRAKENFTS_PERP_BTC_USD",  
    "exchange_id": "KRAKENFTS",  
    "symbol_type": "PERPETUAL",  
    "asset_id_base": "BTC",  
    "asset_id_quote": "USD",  
    "asset_id_unit": "USD",  
    "future_contract_unit": 1,  
    "future_contract_unit_asset": "USD",  
    "data_start": "2019-10-30",  
    "data_end": "2021-03-03",  
    "data_quote_start": "2019-10-30T16:53:10.3262317+00:00",  
    "data_quote_end": "2021-03-03T13:51:45.697+00:00",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317+00:00",  
    "data_orderbook_end": "2020-08-05T14:37:32.008+00:00",  
    "data_trade_start": "2019-10-30T16:38:52.162+00:00",  
    "data_trade_end": "2021-03-03T13:46:25.781+00:00",  
    "symbol_id_exchange": "pi_xbtusd",  
    "asset_id_base_exchange": "XBT",  
    "asset_id_quote_exchange": "USD",  
    "price_precision": 0.1,  
    "size_precision": 1  
  },  
  {  
    "symbol_id": "POLONIEX_SPOT_LTC_USDC",  
    "exchange_id": "POLONIEX",  
    "symbol_type": "SPOT",  
    "asset_id_base": "LTC",  
    "asset_id_quote": "USDC",  
    "data_start": "2018-11-20",  
    "data_end": "2021-03-01",  
    "data_quote_start": "2018-11-20T15:24:58.4128803+00:00",  
    "data_quote_end": "2021-03-01T16:07:09.3475456+00:00",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803+00:00",  
    "data_orderbook_end": "2020-08-05T14:37:20.269578+00:00",  
    "data_trade_start": "2018-11-20T15:25:38+00:00",  
    "data_trade_end": "2021-03-01T16:03:18+00:00",  
    "symbol_id_exchange": "USDC_LTC",  
    "asset_id_base_exchange": "LTC",  
    "asset_id_quote_exchange": "USDC",  
    "price_precision": 1e-8,  
    "size_precision": 1e-8  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol identifier.

**exchange\_id** stringnullable

Gets or sets the exchange identifier.

**symbol\_type** stringnullable

Gets or sets the symbol type.

**asset\_id\_base** stringnullable

Gets or sets the base asset identifier.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset identifier.

**asset\_id\_unit** stringnullable

Gets or sets the unit asset identifier.

**future\_contract\_unit** doublenullable

Gets or sets the contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

Gets or sets the asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

Gets or sets the future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Gets or sets a value indicating whether the option type is a call.

**option\_strike\_price** doublenullable

Gets or sets the strike price for options.

**option\_contract\_unit** doublenullable

Gets or sets the contract unit for options.

**option\_exercise\_style** stringnullable

Gets or sets the exercise style for options.

**option\_expiration\_time** date-timenullable

Gets or sets the expiration time for options.

**contract\_delivery\_time** date-timenullable

Gets or sets the delivery time for contracts.

**contract\_unit** doublenullable

Gets or sets the contract unit for contracts.

**contract\_unit\_asset** stringnullable

Gets or sets the asset used as the unit for contracts.

**contract\_id** stringnullable

Gets or sets the contract identifier.

**contract\_display\_name** stringnullable

Gets or sets the display name of the contract.

**contract\_display\_description** stringnullable

Gets or sets the display description of the contract.

**data\_start** stringnullable

Gets the start date of the data in string format ("yyyy-MM-dd").

**data\_end** stringnullable

Gets the end date of the data in string format ("yyyy-MM-dd").

**data\_quote\_start** date-timenullable

Gets or sets the start date of quote data.

**data\_quote\_end** date-timenullable

Gets or sets the end date of quote data.

**data\_orderbook\_start** date-timenullable

Gets or sets the start date of order book data.

**data\_orderbook\_end** date-timenullable

Gets or sets the end date of order book data.

**data\_trade\_start** date-timenullable

Gets or sets the start date of trade data.

**data\_trade\_end** date-timenullable

Gets or sets the end date of trade data.

**index\_id** stringnullable

Gets or sets the index identifier.

**index\_display\_name** stringnullable

Gets or sets the display name of the index.

**index\_display\_description** stringnullable

Gets or sets the display description of the index.

**symbol\_id\_exchange** stringnullable

Gets or sets the symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

Gets or sets the base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

Gets or sets the quote asset identifier in the exchange.

**price\_precision** doublenullable

Gets or sets the price precision.

**size\_precision** doublenullable

Gets or sets the size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "exchange_id": "string",  
    "symbol_type": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "asset_id_unit": "string",  
    "future_contract_unit": 0,  
    "future_contract_unit_asset": "string",  
    "future_delivery_time": "2025-08-12T06:09:09.086Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:09.086Z",  
    "contract_delivery_time": "2025-08-12T06:09:09.086Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:09.086Z",  
    "data_quote_end": "2025-08-12T06:09:09.086Z",  
    "data_orderbook_start": "2025-08-12T06:09:09.086Z",  
    "data_orderbook_end": "2025-08-12T06:09:09.086Z",  
    "data_trade_start": "2025-08-12T06:09:09.086Z",  
    "data_trade_end": "2025-08-12T06:09:09.086Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0  
  }  
]
```

```
[  
  {  
    "symbol_id": "KRAKENFTS_PERP_BTC_USD",  
    "exchange_id": "KRAKENFTS",  
    "symbol_type": "PERPETUAL",  
    "asset_id_base": "BTC",  
    "asset_id_quote": "USD",  
    "asset_id_unit": "USD",  
    "future_contract_unit": 1,  
    "future_contract_unit_asset": "USD",  
    "data_start": "2019-10-30",  
    "data_end": "2021-03-03",  
    "data_quote_start": "2019-10-30T16:53:10.3262317+00:00",  
    "data_quote_end": "2021-03-03T13:51:45.697+00:00",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317+00:00",  
    "data_orderbook_end": "2020-08-05T14:37:32.008+00:00",  
    "data_trade_start": "2019-10-30T16:38:52.162+00:00",  
    "data_trade_end": "2021-03-03T13:46:25.781+00:00",  
    "symbol_id_exchange": "pi_xbtusd",  
    "asset_id_base_exchange": "XBT",  
    "asset_id_quote_exchange": "USD",  
    "price_precision": 0.1,  
    "size_precision": 1  
  },  
  {  
    "symbol_id": "POLONIEX_SPOT_LTC_USDC",  
    "exchange_id": "POLONIEX",  
    "symbol_type": "SPOT",  
    "asset_id_base": "LTC",  
    "asset_id_quote": "USDC",  
    "data_start": "2018-11-20",  
    "data_end": "2021-03-01",  
    "data_quote_start": "2018-11-20T15:24:58.4128803+00:00",  
    "data_quote_end": "2021-03-01T16:07:09.3475456+00:00",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803+00:00",  
    "data_orderbook_end": "2020-08-05T14:37:20.269578+00:00",  
    "data_trade_start": "2018-11-20T15:25:38+00:00",  
    "data_trade_end": "2021-03-01T16:03:18+00:00",  
    "symbol_id_exchange": "USDC_LTC",  
    "asset_id_base_exchange": "LTC",  
    "asset_id_quote_exchange": "USDC",  
    "price_precision": 1e-8,  
    "size_precision": 1e-8  
  }  
]
```

* Schema
* Example (from schema)
* Example response

**Schema**

* Array [

**symbol\_id** stringnullable

Gets or sets the symbol identifier.

**exchange\_id** stringnullable

Gets or sets the exchange identifier.

**symbol\_type** stringnullable

Gets or sets the symbol type.

**asset\_id\_base** stringnullable

Gets or sets the base asset identifier.

**asset\_id\_quote** stringnullable

Gets or sets the quote asset identifier.

**asset\_id\_unit** stringnullable

Gets or sets the unit asset identifier.

**future\_contract\_unit** doublenullable

Gets or sets the contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

Gets or sets the asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

Gets or sets the future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Gets or sets a value indicating whether the option type is a call.

**option\_strike\_price** doublenullable

Gets or sets the strike price for options.

**option\_contract\_unit** doublenullable

Gets or sets the contract unit for options.

**option\_exercise\_style** stringnullable

Gets or sets the exercise style for options.

**option\_expiration\_time** date-timenullable

Gets or sets the expiration time for options.

**contract\_delivery\_time** date-timenullable

Gets or sets the delivery time for contracts.

**contract\_unit** doublenullable

Gets or sets the contract unit for contracts.

**contract\_unit\_asset** stringnullable

Gets or sets the asset used as the unit for contracts.

**contract\_id** stringnullable

Gets or sets the contract identifier.

**contract\_display\_name** stringnullable

Gets or sets the display name of the contract.

**contract\_display\_description** stringnullable

Gets or sets the display description of the contract.

**data\_start** stringnullable

Gets the start date of the data in string format ("yyyy-MM-dd").

**data\_end** stringnullable

Gets the end date of the data in string format ("yyyy-MM-dd").

**data\_quote\_start** date-timenullable

Gets or sets the start date of quote data.

**data\_quote\_end** date-timenullable

Gets or sets the end date of quote data.

**data\_orderbook\_start** date-timenullable

Gets or sets the start date of order book data.

**data\_orderbook\_end** date-timenullable

Gets or sets the end date of order book data.

**data\_trade\_start** date-timenullable

Gets or sets the start date of trade data.

**data\_trade\_end** date-timenullable

Gets or sets the end date of trade data.

**index\_id** stringnullable

Gets or sets the index identifier.

**index\_display\_name** stringnullable

Gets or sets the display name of the index.

**index\_display\_description** stringnullable

Gets or sets the display description of the index.

**symbol\_id\_exchange** stringnullable

Gets or sets the symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

Gets or sets the base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

Gets or sets the quote asset identifier in the exchange.

**price\_precision** doublenullable

Gets or sets the price precision.

**size\_precision** doublenullable

Gets or sets the size precision.

* ]

```
[  
  {  
    "symbol_id": "string",  
    "exchange_id": "string",  
    "symbol_type": "string",  
    "asset_id_base": "string",  
    "asset_id_quote": "string",  
    "asset_id_unit": "string",  
    "future_contract_unit": 0,  
    "future_contract_unit_asset": "string",  
    "future_delivery_time": "2025-08-12T06:09:09.087Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:09.087Z",  
    "contract_delivery_time": "2025-08-12T06:09:09.087Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:09.087Z",  
    "data_quote_end": "2025-08-12T06:09:09.087Z",  
    "data_orderbook_start": "2025-08-12T06:09:09.087Z",  
    "data_orderbook_end": "2025-08-12T06:09:09.087Z",  
    "data_trade_start": "2025-08-12T06:09:09.087Z",  
    "data_trade_end": "2025-08-12T06:09:09.087Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0  
  }  
]
```

```
[  
  {  
    "symbol_id": "KRAKENFTS_PERP_BTC_USD",  
    "exchange_id": "KRAKENFTS",  
    "symbol_type": "PERPETUAL",  
    "asset_id_base": "BTC",  
    "asset_id_quote": "USD",  
    "asset_id_unit": "USD",  
    "future_contract_unit": 1,  
    "future_contract_unit_asset": "USD",  
    "data_start": "2019-10-30",  
    "data_end": "2021-03-03",  
    "data_quote_start": "2019-10-30T16:53:10.3262317+00:00",  
    "data_quote_end": "2021-03-03T13:51:45.697+00:00",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317+00:00",  
    "data_orderbook_end": "2020-08-05T14:37:32.008+00:00",  
    "data_trade_start": "2019-10-30T16:38:52.162+00:00",  
    "data_trade_end": "2021-03-03T13:46:25.781+00:00",  
    "symbol_id_exchange": "pi_xbtusd",  
    "asset_id_base_exchange": "XBT",  
    "asset_id_quote_exchange": "USD",  
    "price_precision": 0.1,  
    "size_precision": 1  
  },  
  {  
    "symbol_id": "POLONIEX_SPOT_LTC_USDC",  
    "exchange_id": "POLONIEX",  
    "symbol_type": "SPOT",  
    "asset_id_base": "LTC",  
    "asset_id_quote": "USDC",  
    "data_start": "2018-11-20",  
    "data_end": "2021-03-01",  
    "data_quote_start": "2018-11-20T15:24:58.4128803+00:00",  
    "data_quote_end": "2021-03-01T16:07:09.3475456+00:00",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803+00:00",  
    "data_orderbook_end": "2020-08-05T14:37:20.269578+00:00",  
    "data_trade_start": "2018-11-20T15:25:38+00:00",  
    "data_trade_end": "2021-03-01T16:03:18+00:00",  
    "symbol_id_exchange": "USDC_LTC",  
    "asset_id_base_exchange": "LTC",  
    "asset_id_quote_exchange": "USDC",  
    "price_precision": 1e-8,  
    "size_precision": 1e-8  
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

List all schemas](/flat-files-api/rest-api/list-all-schemas)[Next

Data Storage](/flat-files-api/rest-api/data-storage)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.