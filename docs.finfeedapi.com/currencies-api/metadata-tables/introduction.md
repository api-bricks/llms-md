Introduction | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Currencies API](/currencies-api/)
* [Authentication](/currencies-api/authentication)
* [Metadata Tables](/currencies-api/metadata-tables/introduction)

  + [Introduction](/currencies-api/metadata-tables/introduction)
  + [List of Assets](/currencies-api/metadata-tables/assets)
  + [assets](/currencies-api/metadata-tables/assets/assets-0)
* [Realtime REST API](/currencies-api/rest-api-realtime/fx-realtime-rest-api)
* [Historical REST API](/currencies-api/rest-api-historical/fx-historical-rest-api)
* [Websocket API](/currencies-api/websocket/)
* [JSON RPC](/currencies-api/jsonrpc-api)

* Metadata Tables

On this page

Currencies API Metadata
=======================

This section provides downloadable metadata files for the FinFeedAPI Currencies API.

Available Downloads[​](/currencies-api/metadata-tables/introduction#available-downloads "Direct link to Available Downloads")
-----------------------------------------------------------------------------------------------------------------------------

### Assets CSV[​](/currencies-api/metadata-tables/introduction#assets-csv "Direct link to Assets CSV")

Download the complete list of all supported assets:

* **[Assets.csv](/assets/files/Assets-f3ec53a5ac124881994dc2bfc9122f8d.csv)** - Complete list of all supported assets

The Assets.csv file contains the following columns:

* `asset_id` - Unique identifier for the asset
* `name` - Name of the asset
* `type_is_crypto` - Whether the asset is a cryptocurrency (true/false)

info

These CSV files are automatically updated from the FinFeedAPI to ensure you always have the most current metadata available.

tip

You can use these CSV files to:

* Build reference databases for your applications
* Validate asset data
* Create lookup tables for your trading systems
* Generate reports and analytics

API Access[​](/currencies-api/metadata-tables/introduction#api-access "Direct link to API Access")
--------------------------------------------------------------------------------------------------

You can also access this data programmatically through the API endpoint:

* **GET /v1/assets** - List all assets

For more information about the Currencies API, see the [main documentation](/currencies-api/index).

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Authentication](/currencies-api/authentication)[Next

Introduction](/currencies-api/metadata-tables/introduction)

* [Available Downloads](/currencies-api/metadata-tables/introduction#available-downloads)
  + [Assets CSV](/currencies-api/metadata-tables/introduction#assets-csv)
* [API Access](/currencies-api/metadata-tables/introduction#api-access)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.