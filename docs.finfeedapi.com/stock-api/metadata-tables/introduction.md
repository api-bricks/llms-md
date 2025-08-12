Metadata Tables | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Stock Data API](/stock-api/)
* [Authentication](/stock-api/authentication)
* [Metadata Tables](/stock-api/metadata-tables/introduction)

  + [Overview](/stock-api/metadata-tables/introduction)
  + [List of Exchanges](/stock-api/metadata-tables/exchanges)
  + [List of Symbols per Exchange](/stock-api/metadata-tables/symbols/alxb)
* [Historical REST API](/stock-api/rest-api-historical/finfeedapi-stock-rest-api)
* [JSON RPC](/stock-api/jsonrpc-api)

* Metadata Tables

On this page

Introduction
============

Welcome to the Metadata Tables section. This area provides comprehensive metadata about exchanges and symbols available through the FinFeedAPI.

Downloadable Metadata[​](/stock-api/metadata-tables/introduction#downloadable-metadata "Direct link to Downloadable Metadata")
------------------------------------------------------------------------------------------------------------------------------

This section provides the updated supported Exchanges and Symbols.

The data included in the CSV files are the same data that you can acquire from:

* **List of exchanges**: <https://api-historical.stock.finfeedapi.com/v1/exchanges>
* **List of symbols**: <https://api-historical.stock.finfeedapi.com/v1/symbols/:exchange_id>

You may download the complete metadata here (CSV files):

* [Exchanges.csv](/assets/files/Exchanges-26c2c7538401ae40f7ef7106bb028913.csv)
* [Symbols.csv](/assets/files/Symbols-e2d17d14d2b8935ef32b742741ce97cb.csv)

Data Structure[​](/stock-api/metadata-tables/introduction#data-structure "Direct link to Data Structure")
---------------------------------------------------------------------------------------------------------

### Exchanges CSV[​](/stock-api/metadata-tables/introduction#exchanges-csv "Direct link to Exchanges CSV")

The Exchanges.csv file contains the following columns:

* `exchange_id` - Unique identifier for the exchange
* `legal_entity_name` - Legal name of the exchange entity
* `iso_country_code` - ISO country code where the exchange is located
* `market_category_code` - Market category classification
* `status` - Current status of the exchange (ACTIVE, INACTIVE, etc.)
* `creation_date` - Date when the exchange was created
* `last_update_date` - Date of the last update

### Symbols CSV[​](/stock-api/metadata-tables/introduction#symbols-csv "Direct link to Symbols CSV")

The Symbols.csv file contains the following columns:

* `symbol_id` - Unique identifier for the symbol
* `exchange_id` - Exchange where the symbol is traded
* `security_category` - Category of the security (Stock, Bond, ETF, etc.)
* `name` - Name of the symbol
* `asset_class` - Asset class classification
* `is_enabled` - Whether the symbol is currently enabled for trading

info

These CSV files are automatically updated from the FinFeedAPI to ensure you always have the most current metadata available.

tip

You can use these CSV files to:

* Build reference databases for your applications
* Validate symbol and exchange data
* Create lookup tables for your trading systems
* Generate reports and analytics

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Authentication](/stock-api/authentication)[Next

Overview](/stock-api/metadata-tables/introduction)

* [Downloadable Metadata](/stock-api/metadata-tables/introduction#downloadable-metadata)
* [Data Structure](/stock-api/metadata-tables/introduction#data-structure)
  + [Exchanges CSV](/stock-api/metadata-tables/introduction#exchanges-csv)
  + [Symbols CSV](/stock-api/metadata-tables/introduction#symbols-csv)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.