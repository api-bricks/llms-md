List all active symbols | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/rest-api/metadata/list-all-active-symbols)

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

    - [Introduction](/market-data/rest-api/metadata/coinapi-market-data-rest-api)
    - [List active symbol mapping for the exchange](/market-data/rest-api/metadata/list-active-symbol-mapping-for-the-exchange)
    - [List all active symbols](/market-data/rest-api/metadata/list-all-active-symbols)
    - [List all asset icons](/market-data/rest-api/metadata/list-all-asset-icons)
    - [List all assets by asset ID](/market-data/rest-api/metadata/list-all-assets-by-asset-id)
    - [List all assets](/market-data/rest-api/metadata/list-all-assets)
    - [List all blockchain chains](/market-data/rest-api/metadata/list-all-blockchain-chains)
    - [List all chains by chain ID](/market-data/rest-api/metadata/list-all-chains-by-chain-id)
    - [List all exchanges by exchange\_id](/market-data/rest-api/metadata/list-all-exchanges-by-exchange-id)
    - [List all exchanges](/market-data/rest-api/metadata/list-all-exchanges)
    - [List all historical symbols for an exchange.](/market-data/rest-api/metadata/list-all-historical-symbols-for-an-exchange)
    - [List of active symbols for the exchange](/market-data/rest-api/metadata/list-of-active-symbols-for-the-exchange)
    - [List of icons for the exchanges](/market-data/rest-api/metadata/list-of-icons-for-the-exchanges)
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
* [Metadata](/market-data/rest-api/metadata/)
* List all active symbols

List all active symbols
=======================

```
GET

/v1/symbols
-----------
```

Retrieves all currently active (listed) symbols, with optional filtering.

info

"price\_precision" and "size\_precision" are data precisions and are not always the same precisions used for trading eg. for the "BINANCE" exchanges.

info

You should not assume that the market data will be always within the resolution provided by the "price\_precision" and "size\_precision". The fact that the precision values can be derived from a posterior implies the fact that this data could be delayed, also it can be changed by the data source without notice and we will immediately deliver data with the new precision while could not update the precision values in this endpoint immediately.

### Symbol identifier[​](/market-data/rest-api/metadata/list-all-active-symbols#symbol-identifier "Direct link to Symbol identifier")

Our symbol identifier is created using a pattern that depends on symbol type.

| Type | `symbol_id` pattern |
| --- | --- |
| SPOT | `{exchange_id}_SPOT_{asset_id_base}_{asset_id_quote}` |
| FUTURES | `{exchange_id}_FTS_{asset_id_base}_{asset_id_quote}_{YYMMDD of future_delivery_time}` |
| OPTION | `{exchange_id}_OPT_{asset_id_base}_{asset_id_quote}_{YYMMDD of option_expiration_time}_{option_strike_price}_{option_type_is_call as C/P}` |
| PERPETUAL | `{exchange_id}_PERP_{asset_id_base}_{asset_id_quote}` |
| INDEX | `{exchange_id}_IDX_{index_id}` |
| CREDIT | `{exchange_id}_CRE_{asset_id_base}` |
| CONTACT | `{exchange_id}_COT_{contract_id}` |

info

In the unlikely event when the "symbol\_id" for more than one market is the same. We will append the additional term (prefixed with the "\_") at the end of the duplicated identifiers to differentiate them.

info

### Symbol types list (enumeration of `symbol_type` output variable)[​](/market-data/rest-api/metadata/list-all-active-symbols#symbol-types-list-enumeration-of-symbol_type-output-variable "Direct link to symbol-types-list-enumeration-of-symbol_type-output-variable")

| Type | Name | Description |
| --- | --- | --- |
| SPOT | FX Spot | Agreement to exchange one asset for another one *(e.g. Buy BTC for USD)* |
| FUTURES | Futures contract | FX Spot derivative contract where traders agree to trade fx spot at predetermined future time |
| OPTION | Option contract | FX Spot derivative contract where traders agree to trade right to require buy or sell of fx spot at agreed price on exercise date |
| PERPETUAL | Perpetual contract | FX Spot derivative contract where traders agree to trade fx spot continously without predetermined future delivery time |
| INDEX | Index | Statistical composite that measures changes in the economy or markets. |
| CREDIT | Credit/Funding | Margin funding contract. Order book displays lending offers and borrow bids. Price represents the daily rate. |
| CONTRACT | Contract | Represents other types of financial instruments *(e.g. spreads, interest rate swap)* |

### Additional output variables for `symbol_type = INDEX`[​](/market-data/rest-api/metadata/list-all-active-symbols#additional-output-variables-for-symbol_type--index "Direct link to additional-output-variables-for-symbol_type--index")

| Variable | Description |
| --- | --- |
| index\_id | Index identifier |
| index\_display\_name | Human readable name of the index *(optional)* |
| index\_display\_description | Description of the index *(optional)* |

### Additional output variables for `symbol_type = FUTURES`[​](/market-data/rest-api/metadata/list-all-active-symbols#additional-output-variables-for-symbol_type--futures "Direct link to additional-output-variables-for-symbol_type--futures")

| Variable | Description |
| --- | --- |
| future\_delivery\_time | Predetermined time of futures contract delivery date in ISO 8601 |
| future\_contract\_unit | Contact size *(eg. 10 BTC if `future_contract_unit` = `10` and `future_contract_unit_asset` = `BTC`)* |
| future\_contract\_unit\_asset | Identifier of the asset used to denominate the contract unit |

### Additional output variables for `symbol_type = PERPETUAL`[​](/market-data/rest-api/metadata/list-all-active-symbols#additional-output-variables-for-symbol_type--perpetual "Direct link to additional-output-variables-for-symbol_type--perpetual")

| Variable | Description |
| --- | --- |
| future\_contract\_unit | Contact size *(eg. 10 BTC if `future_contract_unit` = `10` and `future_contract_unit_asset` = `BTC`)* |
| future\_contract\_unit\_asset | Identifier of the asset used to denominate the contract unit |

### Additional output variables for `symbol_type = OPTION`[​](/market-data/rest-api/metadata/list-all-active-symbols#additional-output-variables-for-symbol_type--option "Direct link to additional-output-variables-for-symbol_type--option")

| Variable | Description |
| --- | --- |
| option\_type\_is\_call | Boolean value representing option type. `true` for Call options, `false` for Put options |
| option\_strike\_price | Price at which option contract can be exercised |
| option\_contract\_unit | Base asset amount of underlying spot which single option represents |
| option\_exercise\_style | Option exercise style. Can be `EUROPEAN` or `AMERICAN` |
| option\_expiration\_time | Option contract expiration time in ISO 8601 |

### Additional output variables for `symbol_type = CONTRACT`[​](/market-data/rest-api/metadata/list-all-active-symbols#additional-output-variables-for-symbol_type--contract "Direct link to additional-output-variables-for-symbol_type--contract")

| Variable | Description |
| --- | --- |
| contract\_delivery\_time | Predetermined time of contract delivery date in ISO 8601 |
| contract\_unit | Contact size *(eg. 10 BTC if `contract_unit` = `10` and `contract_unit_asset` = `BTC`)* |
| contract\_unit\_asset | Identifier of the asset used to denominate the contract unit |
| contract\_id | Identifier of contract by the exchange |

Request[​](/market-data/rest-api/metadata/list-all-active-symbols#request "Direct link to Request")
---------------------------------------------------------------------------------------------------

### Query Parameters

**filter\_symbol\_id** string

Comma or semicolon delimited parts of symbol identifier used to filter response. (optional, eg. `BITSTAMP`\_ or `BINANCE_SPOT_`)

**filter\_exchange\_id** string

The filter for exchange ID.

**filter\_asset\_id** string

The filter for asset ID.

Responses[​](/market-data/rest-api/metadata/list-all-active-symbols#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------------------

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

**symbol\_id** stringnullable

The symbol identifier.

**exchange\_id** stringnullable

The exchange identifier.

**symbol\_type** stringnullable

The symbol type.

**asset\_id\_base** stringnullable

The base asset identifier.

**asset\_id\_quote** stringnullable

The quote asset identifier.

**asset\_id\_unit** stringnullable

The unit asset identifier.

**future\_contract\_unit** doublenullable

The contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

The asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

The future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Indicates whether the option type is a call.

**option\_strike\_price** doublenullable

The strike price for options.

**option\_contract\_unit** doublenullable

The contract unit for options.

**option\_exercise\_style** stringnullable

The exercise style for options.

**option\_expiration\_time** date-timenullable

The expiration time for options.

**contract\_delivery\_time** date-timenullable

The delivery time for contracts.

**contract\_unit** doublenullable

The contract unit for contracts.

**contract\_unit\_asset** stringnullable

The asset used as the unit for contracts.

**contract\_id** stringnullable

The contract identifier.

**contract\_display\_name** stringnullable

The display name of the contract.

**contract\_display\_description** stringnullable

The display description of the contract.

**data\_start** stringnullable

**data\_end** stringnullable

**data\_quote\_start** date-timenullable

The start date of quote data.

**data\_quote\_end** date-timenullable

The end date of quote data.

**data\_orderbook\_start** date-timenullable

The start date of order book data.

**data\_orderbook\_end** date-timenullable

The end date of order book data.

**data\_trade\_start** date-timenullable

The start date of trade data.

**data\_trade\_end** date-timenullable

The end date of trade data.

**index\_id** stringnullable

The index identifier.

**index\_display\_name** stringnullable

The display name of the index.

**index\_display\_description** stringnullable

The display description of the index.

**volume\_1hrs** doublenullable

The volume in the last 1 hour.

**volume\_1hrs\_usd** doublenullable

The volume in USD in the last 1 hour.

**volume\_1day** doublenullable

The volume in the last 1 day.

**volume\_1day\_usd** doublenullable

The volume in USD in the last 1 day.

**volume\_1mth** doublenullable

The volume in the last 1 month.

**volume\_1mth\_usd** doublenullable

The volume in USD in the last 1 month.

**price** doublenullable

The price.

**symbol\_id\_exchange** stringnullable

The symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

The base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

The quote asset identifier in the exchange.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

**raw\_kvp**

object

nullable

Not normalized raw kvp data.

**property name\*** string

**volume\_to\_usd** doublenullable

Volume unit in USD.

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
    "future_delivery_time": "2025-08-12T06:09:08.724Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:08.724Z",  
    "contract_delivery_time": "2025-08-12T06:09:08.724Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.724Z",  
    "data_quote_end": "2025-08-12T06:09:08.724Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.724Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.724Z",  
    "data_trade_start": "2025-08-12T06:09:08.724Z",  
    "data_trade_end": "2025-08-12T06:09:08.724Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "volume_1hrs": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth": 0,  
    "volume_1mth_usd": 0,  
    "price": 0,  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0,  
    "raw_kvp": {},  
    "volume_to_usd": 0  
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
    "data_quote_start": "2019-10-30T16:53:10.3262317Z",  
    "data_quote_end": "2021-03-03T13:51:45.6970000Z",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317Z",  
    "data_orderbook_end": "2020-08-05T14:37:32.0080000Z",  
    "data_trade_start": "2019-10-30T16:38:52.1620000Z",  
    "data_trade_end": "2021-03-03T13:46:25.7810000Z",  
    "volume_1hrs": 22897091,  
    "volume_1hrs_usd": 22897091,  
    "volume_1day": 459390289,  
    "volume_1day_usd": 459390289,  
    "volume_1mth": 12875674995,  
    "volume_1mth_usd": 12875674995,  
    "price": 51266,  
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
    "data_quote_start": "2018-11-20T15:24:58.4128803Z",  
    "data_quote_end": "2021-03-01T16:07:09.3475456Z",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803Z",  
    "data_orderbook_end": "2020-08-05T14:37:20.2695780Z",  
    "data_trade_start": "2018-11-20T15:25:38.0000000Z",  
    "data_trade_end": "2021-03-01T16:03:18.0000000Z",  
    "volume_1hrs": 51.68645899,  
    "volume_1hrs_usd": 9036.44,  
    "volume_1day": 465.568863,  
    "volume_1day_usd": 81396.28,  
    "volume_1mth": 22528.27638495,  
    "volume_1mth_usd": 3938661,  
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

The symbol identifier.

**exchange\_id** stringnullable

The exchange identifier.

**symbol\_type** stringnullable

The symbol type.

**asset\_id\_base** stringnullable

The base asset identifier.

**asset\_id\_quote** stringnullable

The quote asset identifier.

**asset\_id\_unit** stringnullable

The unit asset identifier.

**future\_contract\_unit** doublenullable

The contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

The asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

The future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Indicates whether the option type is a call.

**option\_strike\_price** doublenullable

The strike price for options.

**option\_contract\_unit** doublenullable

The contract unit for options.

**option\_exercise\_style** stringnullable

The exercise style for options.

**option\_expiration\_time** date-timenullable

The expiration time for options.

**contract\_delivery\_time** date-timenullable

The delivery time for contracts.

**contract\_unit** doublenullable

The contract unit for contracts.

**contract\_unit\_asset** stringnullable

The asset used as the unit for contracts.

**contract\_id** stringnullable

The contract identifier.

**contract\_display\_name** stringnullable

The display name of the contract.

**contract\_display\_description** stringnullable

The display description of the contract.

**data\_start** stringnullable

**data\_end** stringnullable

**data\_quote\_start** date-timenullable

The start date of quote data.

**data\_quote\_end** date-timenullable

The end date of quote data.

**data\_orderbook\_start** date-timenullable

The start date of order book data.

**data\_orderbook\_end** date-timenullable

The end date of order book data.

**data\_trade\_start** date-timenullable

The start date of trade data.

**data\_trade\_end** date-timenullable

The end date of trade data.

**index\_id** stringnullable

The index identifier.

**index\_display\_name** stringnullable

The display name of the index.

**index\_display\_description** stringnullable

The display description of the index.

**volume\_1hrs** doublenullable

The volume in the last 1 hour.

**volume\_1hrs\_usd** doublenullable

The volume in USD in the last 1 hour.

**volume\_1day** doublenullable

The volume in the last 1 day.

**volume\_1day\_usd** doublenullable

The volume in USD in the last 1 day.

**volume\_1mth** doublenullable

The volume in the last 1 month.

**volume\_1mth\_usd** doublenullable

The volume in USD in the last 1 month.

**price** doublenullable

The price.

**symbol\_id\_exchange** stringnullable

The symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

The base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

The quote asset identifier in the exchange.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

**raw\_kvp**

object

nullable

Not normalized raw kvp data.

**property name\*** string

**volume\_to\_usd** doublenullable

Volume unit in USD.

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
    "future_delivery_time": "2025-08-12T06:09:08.725Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:08.725Z",  
    "contract_delivery_time": "2025-08-12T06:09:08.725Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.725Z",  
    "data_quote_end": "2025-08-12T06:09:08.725Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.725Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.725Z",  
    "data_trade_start": "2025-08-12T06:09:08.725Z",  
    "data_trade_end": "2025-08-12T06:09:08.725Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "volume_1hrs": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth": 0,  
    "volume_1mth_usd": 0,  
    "price": 0,  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0,  
    "raw_kvp": {},  
    "volume_to_usd": 0  
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
    "data_quote_start": "2019-10-30T16:53:10.3262317Z",  
    "data_quote_end": "2021-03-03T13:51:45.6970000Z",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317Z",  
    "data_orderbook_end": "2020-08-05T14:37:32.0080000Z",  
    "data_trade_start": "2019-10-30T16:38:52.1620000Z",  
    "data_trade_end": "2021-03-03T13:46:25.7810000Z",  
    "volume_1hrs": 22897091,  
    "volume_1hrs_usd": 22897091,  
    "volume_1day": 459390289,  
    "volume_1day_usd": 459390289,  
    "volume_1mth": 12875674995,  
    "volume_1mth_usd": 12875674995,  
    "price": 51266,  
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
    "data_quote_start": "2018-11-20T15:24:58.4128803Z",  
    "data_quote_end": "2021-03-01T16:07:09.3475456Z",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803Z",  
    "data_orderbook_end": "2020-08-05T14:37:20.2695780Z",  
    "data_trade_start": "2018-11-20T15:25:38.0000000Z",  
    "data_trade_end": "2021-03-01T16:03:18.0000000Z",  
    "volume_1hrs": 51.68645899,  
    "volume_1hrs_usd": 9036.44,  
    "volume_1day": 465.568863,  
    "volume_1day_usd": 81396.28,  
    "volume_1mth": 22528.27638495,  
    "volume_1mth_usd": 3938661,  
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

The symbol identifier.

**exchange\_id** stringnullable

The exchange identifier.

**symbol\_type** stringnullable

The symbol type.

**asset\_id\_base** stringnullable

The base asset identifier.

**asset\_id\_quote** stringnullable

The quote asset identifier.

**asset\_id\_unit** stringnullable

The unit asset identifier.

**future\_contract\_unit** doublenullable

The contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

The asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

The future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Indicates whether the option type is a call.

**option\_strike\_price** doublenullable

The strike price for options.

**option\_contract\_unit** doublenullable

The contract unit for options.

**option\_exercise\_style** stringnullable

The exercise style for options.

**option\_expiration\_time** date-timenullable

The expiration time for options.

**contract\_delivery\_time** date-timenullable

The delivery time for contracts.

**contract\_unit** doublenullable

The contract unit for contracts.

**contract\_unit\_asset** stringnullable

The asset used as the unit for contracts.

**contract\_id** stringnullable

The contract identifier.

**contract\_display\_name** stringnullable

The display name of the contract.

**contract\_display\_description** stringnullable

The display description of the contract.

**data\_start** stringnullable

**data\_end** stringnullable

**data\_quote\_start** date-timenullable

The start date of quote data.

**data\_quote\_end** date-timenullable

The end date of quote data.

**data\_orderbook\_start** date-timenullable

The start date of order book data.

**data\_orderbook\_end** date-timenullable

The end date of order book data.

**data\_trade\_start** date-timenullable

The start date of trade data.

**data\_trade\_end** date-timenullable

The end date of trade data.

**index\_id** stringnullable

The index identifier.

**index\_display\_name** stringnullable

The display name of the index.

**index\_display\_description** stringnullable

The display description of the index.

**volume\_1hrs** doublenullable

The volume in the last 1 hour.

**volume\_1hrs\_usd** doublenullable

The volume in USD in the last 1 hour.

**volume\_1day** doublenullable

The volume in the last 1 day.

**volume\_1day\_usd** doublenullable

The volume in USD in the last 1 day.

**volume\_1mth** doublenullable

The volume in the last 1 month.

**volume\_1mth\_usd** doublenullable

The volume in USD in the last 1 month.

**price** doublenullable

The price.

**symbol\_id\_exchange** stringnullable

The symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

The base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

The quote asset identifier in the exchange.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

**raw\_kvp**

object

nullable

Not normalized raw kvp data.

**property name\*** string

**volume\_to\_usd** doublenullable

Volume unit in USD.

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
    "future_delivery_time": "2025-08-12T06:09:08.726Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:08.726Z",  
    "contract_delivery_time": "2025-08-12T06:09:08.726Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.726Z",  
    "data_quote_end": "2025-08-12T06:09:08.726Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.726Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.726Z",  
    "data_trade_start": "2025-08-12T06:09:08.726Z",  
    "data_trade_end": "2025-08-12T06:09:08.726Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "volume_1hrs": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth": 0,  
    "volume_1mth_usd": 0,  
    "price": 0,  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0,  
    "raw_kvp": {},  
    "volume_to_usd": 0  
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
    "data_quote_start": "2019-10-30T16:53:10.3262317Z",  
    "data_quote_end": "2021-03-03T13:51:45.6970000Z",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317Z",  
    "data_orderbook_end": "2020-08-05T14:37:32.0080000Z",  
    "data_trade_start": "2019-10-30T16:38:52.1620000Z",  
    "data_trade_end": "2021-03-03T13:46:25.7810000Z",  
    "volume_1hrs": 22897091,  
    "volume_1hrs_usd": 22897091,  
    "volume_1day": 459390289,  
    "volume_1day_usd": 459390289,  
    "volume_1mth": 12875674995,  
    "volume_1mth_usd": 12875674995,  
    "price": 51266,  
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
    "data_quote_start": "2018-11-20T15:24:58.4128803Z",  
    "data_quote_end": "2021-03-01T16:07:09.3475456Z",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803Z",  
    "data_orderbook_end": "2020-08-05T14:37:20.2695780Z",  
    "data_trade_start": "2018-11-20T15:25:38.0000000Z",  
    "data_trade_end": "2021-03-01T16:03:18.0000000Z",  
    "volume_1hrs": 51.68645899,  
    "volume_1hrs_usd": 9036.44,  
    "volume_1day": 465.568863,  
    "volume_1day_usd": 81396.28,  
    "volume_1mth": 22528.27638495,  
    "volume_1mth_usd": 3938661,  
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

The symbol identifier.

**exchange\_id** stringnullable

The exchange identifier.

**symbol\_type** stringnullable

The symbol type.

**asset\_id\_base** stringnullable

The base asset identifier.

**asset\_id\_quote** stringnullable

The quote asset identifier.

**asset\_id\_unit** stringnullable

The unit asset identifier.

**future\_contract\_unit** doublenullable

The contract unit for futures.

**future\_contract\_unit\_asset** stringnullable

The asset used as the unit for futures contract.

**future\_delivery\_time** date-timenullable

The future delivery time for futures contract.

**option\_type\_is\_call** booleannullable

Indicates whether the option type is a call.

**option\_strike\_price** doublenullable

The strike price for options.

**option\_contract\_unit** doublenullable

The contract unit for options.

**option\_exercise\_style** stringnullable

The exercise style for options.

**option\_expiration\_time** date-timenullable

The expiration time for options.

**contract\_delivery\_time** date-timenullable

The delivery time for contracts.

**contract\_unit** doublenullable

The contract unit for contracts.

**contract\_unit\_asset** stringnullable

The asset used as the unit for contracts.

**contract\_id** stringnullable

The contract identifier.

**contract\_display\_name** stringnullable

The display name of the contract.

**contract\_display\_description** stringnullable

The display description of the contract.

**data\_start** stringnullable

**data\_end** stringnullable

**data\_quote\_start** date-timenullable

The start date of quote data.

**data\_quote\_end** date-timenullable

The end date of quote data.

**data\_orderbook\_start** date-timenullable

The start date of order book data.

**data\_orderbook\_end** date-timenullable

The end date of order book data.

**data\_trade\_start** date-timenullable

The start date of trade data.

**data\_trade\_end** date-timenullable

The end date of trade data.

**index\_id** stringnullable

The index identifier.

**index\_display\_name** stringnullable

The display name of the index.

**index\_display\_description** stringnullable

The display description of the index.

**volume\_1hrs** doublenullable

The volume in the last 1 hour.

**volume\_1hrs\_usd** doublenullable

The volume in USD in the last 1 hour.

**volume\_1day** doublenullable

The volume in the last 1 day.

**volume\_1day\_usd** doublenullable

The volume in USD in the last 1 day.

**volume\_1mth** doublenullable

The volume in the last 1 month.

**volume\_1mth\_usd** doublenullable

The volume in USD in the last 1 month.

**price** doublenullable

The price.

**symbol\_id\_exchange** stringnullable

The symbol identifier in the exchange.

**asset\_id\_base\_exchange** stringnullable

The base asset identifier in the exchange.

**asset\_id\_quote\_exchange** stringnullable

The quote asset identifier in the exchange.

**price\_precision** doublenullable

The price precision.

**size\_precision** doublenullable

The size precision.

**raw\_kvp**

object

nullable

Not normalized raw kvp data.

**property name\*** string

**volume\_to\_usd** doublenullable

Volume unit in USD.

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
    "future_delivery_time": "2025-08-12T06:09:08.727Z",  
    "option_type_is_call": true,  
    "option_strike_price": 0,  
    "option_contract_unit": 0,  
    "option_exercise_style": "string",  
    "option_expiration_time": "2025-08-12T06:09:08.727Z",  
    "contract_delivery_time": "2025-08-12T06:09:08.727Z",  
    "contract_unit": 0,  
    "contract_unit_asset": "string",  
    "contract_id": "string",  
    "contract_display_name": "string",  
    "contract_display_description": "string",  
    "data_start": "string",  
    "data_end": "string",  
    "data_quote_start": "2025-08-12T06:09:08.727Z",  
    "data_quote_end": "2025-08-12T06:09:08.727Z",  
    "data_orderbook_start": "2025-08-12T06:09:08.727Z",  
    "data_orderbook_end": "2025-08-12T06:09:08.727Z",  
    "data_trade_start": "2025-08-12T06:09:08.727Z",  
    "data_trade_end": "2025-08-12T06:09:08.727Z",  
    "index_id": "string",  
    "index_display_name": "string",  
    "index_display_description": "string",  
    "volume_1hrs": 0,  
    "volume_1hrs_usd": 0,  
    "volume_1day": 0,  
    "volume_1day_usd": 0,  
    "volume_1mth": 0,  
    "volume_1mth_usd": 0,  
    "price": 0,  
    "symbol_id_exchange": "string",  
    "asset_id_base_exchange": "string",  
    "asset_id_quote_exchange": "string",  
    "price_precision": 0,  
    "size_precision": 0,  
    "raw_kvp": {},  
    "volume_to_usd": 0  
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
    "data_quote_start": "2019-10-30T16:53:10.3262317Z",  
    "data_quote_end": "2021-03-03T13:51:45.6970000Z",  
    "data_orderbook_start": "2019-10-30T16:53:10.3262317Z",  
    "data_orderbook_end": "2020-08-05T14:37:32.0080000Z",  
    "data_trade_start": "2019-10-30T16:38:52.1620000Z",  
    "data_trade_end": "2021-03-03T13:46:25.7810000Z",  
    "volume_1hrs": 22897091,  
    "volume_1hrs_usd": 22897091,  
    "volume_1day": 459390289,  
    "volume_1day_usd": 459390289,  
    "volume_1mth": 12875674995,  
    "volume_1mth_usd": 12875674995,  
    "price": 51266,  
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
    "data_quote_start": "2018-11-20T15:24:58.4128803Z",  
    "data_quote_end": "2021-03-01T16:07:09.3475456Z",  
    "data_orderbook_start": "2018-11-20T15:24:58.4128803Z",  
    "data_orderbook_end": "2020-08-05T14:37:20.2695780Z",  
    "data_trade_start": "2018-11-20T15:25:38.0000000Z",  
    "data_trade_end": "2021-03-01T16:03:18.0000000Z",  
    "volume_1hrs": 51.68645899,  
    "volume_1hrs_usd": 9036.44,  
    "volume_1day": 465.568863,  
    "volume_1day_usd": 81396.28,  
    "volume_1mth": 22528.27638495,  
    "volume_1mth_usd": 3938661,  
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

List active symbol mapping for the exchange](/market-data/rest-api/metadata/list-active-symbol-mapping-for-the-exchange)[Next

List all asset icons](/market-data/rest-api/metadata/list-all-asset-icons)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.