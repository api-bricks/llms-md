Import data to Google Sheets/Excel | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/import-data-to-google-sheets-excel)

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

  + [Introduction](/market-data/how-to-guides/)
  + [Acquire exchange rates with different programming languages](/market-data/how-to-guides/acquire-exchange-rates-with-different-programming-languages)
  + [Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react)
  + [Building a cryptocurrency exchange comparison tool using Market Data API](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api)
  + [Creating a historical crypto price chart using CoinAPI and D3.js](/market-data/how-to-guides/creating-historical-crypto-price-chart-using-CoinAPI-and-D3-js)
  + [Fetching market data with KNIME](/market-data/how-to-guides/fetching-market-data-with-knime)
  + [Get Historical OHLCV Data Using CoinAPI](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi)
  + [Get symbol funding rate metric data using CoinAPI](/market-data/how-to-guides/get-symbol-funding-rate-metric-data)
  + [Import API into Postman](/market-data/how-to-guides/import-api-into-postman)
  + [Import data to Google Sheets/Excel](/market-data/how-to-guides/import-data-to-google-sheets-excel)
  + [Real-time data visualization with javascript](/market-data/how-to-guides/real-time-data-visualization-with-javascript)
  + [Real-time trades stream using WebSocket with different languages](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages)
  + [Retrieve and analyze crypto order book data using a cryptocurrency API](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [How-to guides](/market-data/how-to-guides/)
* Import data to Google Sheets/Excel

On this page

Import data to Google Sheets/Excel
==================================

Introduction[​](/market-data/how-to-guides/import-data-to-google-sheets-excel#introduction "Direct link to Introduction")
-------------------------------------------------------------------------------------------------------------------------

There are various methods to access market data, including utilizing programming languages or tools that enable REST API requests.

In this guide, we will specifically concentrate on extracting data in `CSV` *(comma-separated-values)* format
using a simple approach that involves accessing data directly through a `web browser`.

`CSV` is widely used due to its simplicity and compatibility with various spreadsheet applications like Microsoft Excel and Google Sheets.

Getting started[​](/market-data/how-to-guides/import-data-to-google-sheets-excel#getting-started "Direct link to Getting started")
----------------------------------------------------------------------------------------------------------------------------------

Before diving into the tutorial, ensure you have:

* Web browser installed: `google chrome`, `firefox`, `microsoft edge`, or any other
* A CoinAPI key (obtainable by signing up on the CoinAPI website)
* A spreadsheet application like `Microsoft Excel` or `Google Sheets`

Retrieve BTC Exchange Rates in .csv format via web browser[​](/market-data/how-to-guides/import-data-to-google-sheets-excel#retrieve-btc-exchange-rates-in-csv-format-via-web-browser "Direct link to Retrieve BTC Exchange Rates in .csv format via web browser")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

It is possible to control the format of data by using [output\_format](/market-data/rest-api#output-data-format) variable in query string parameters.   
To get `BTC` exchange rates in `csv` format, copy and paste the below URL to the address bar of your web browser:

`https://rest.coinapi.io/v1/exchangerate/BTC?apikey=YOUR_API_KEY-ed802af4-e855-4505-AEA&output_format=csv`

![Address bar with exchange rate formatted to csv](/assets/images/csv_format_to_excel-8f249cef2abc54a6e8466df3b155ca8e.jpg)

**Note:** Don't forget to *replace `YOUR-API-KEY` with your actual API key.*

Simple then press `ctrl`+`a` or `command`+`a` to select exchange rates,   
then press `ctrl` + `c` to copy data.

![Exchange rate data selected](/assets/images/csv_format_to_excel_selected-a0d9e12e0031fd75d961b321b0dbb060.jpg)

After obtaining the data, you can seamlessly paste it directly into any text editor.

![BTC exchange rates in notepad](/assets/images/copy-and-paste-to-notepad-f4b683e9b9e03d78b0901d0cf79ef129.jpg)

Then, select the `Save As` option, and don't forget to include the `.csv` file extension.

![BTC exchange rates copied over notepad](/assets/images/notepad-save-as-csv-ae6677193327eee695914ce5e3dcfcb7.jpg)

CSV import: Microsoft Excel[​](/market-data/how-to-guides/import-data-to-google-sheets-excel#csv-import-microsoft-excel "Direct link to CSV import: Microsoft Excel")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

To import the `.csv` file into the MS Excel application, navigate to the `Data` tab, and choose the `From Text/CSV` option.

![Import from Text/CSV in Excel](/assets/images/import-excel-1-516869d7033ac1b3b4eb2e433b7183c3.jpg)

Select your `.csv` file which includes BTC exchange rate data in `csv` format.

![Import from Text/CSV in Excel](/assets/images/import-excel-2-ecd8017c8a3bd78a9de591741609e74b.jpg)

Verify the output of import in the preview window.

![Import Text/CSV preview window](/assets/images/import-excel-3-08be25ba0d198d718ce62e9ccdcbf66e.jpg)

With these simple steps, you can now efficiently work with and analyze the market data in a familiar spreadsheet environment,
empowering you to make informed decisions based on the exchange rate information.

CSV import: Google Sheets[​](/market-data/how-to-guides/import-data-to-google-sheets-excel#csv-import-google-sheets "Direct link to CSV import: Google Sheets")
---------------------------------------------------------------------------------------------------------------------------------------------------------------

To import the `.csv` file into the Google Sheets application, navigate to the `File` menu.

![Google Sheets default window](/assets/images/google-import-1-c52c9ad095b8e6fe6d54325f3ab8bc38.jpg)

Within that menu, select the `Import` option.

![Google Sheets default window](/assets/images/google-import-2-103ef4bb23bde47546d3785de8680e9c.jpg)

Upload your `.csv` file which includes BTC exchange rate data.

![Google Sheets default window](/assets/images/google-import-3-0ce924e909bb48b28ede3ae3da91c0bf.jpg)

Make sure to set the correct `Import location` and `Separator type`, then press `Import data`.

![Google Sheets default window](/assets/images/google-import-4-f4979085d8de96f17f1dbbb7381c8314.jpg)

Here's the final result:

![Google Sheets default window](/assets/images/google-import-5-2d592839928cf87e338e8c919a4f37bb.jpg)

With these simple steps, you can now efficiently work with and analyze the market data in a familiar spreadsheet environment,
empowering you to make informed decisions based on the exchange rate information.

Summary[​](/market-data/how-to-guides/import-data-to-google-sheets-excel#summary "Direct link to Summary")
----------------------------------------------------------------------------------------------------------

We have explored a simple approach to accessing market data in CSV format directly through a web browser.   
By utilizing this method, you can easily extract the data you need for analysis and integrate it with various spreadsheet applications like `Microsoft Excel` or `Google Sheets`.

While the simple approach through a web browser provides easy access to market data in CSV format,
there is [cryptotick specialized platform](https://www.cryptotick.com/) that offers a wide range of market data types in the `csv` format,
including `quotes`, `trades`, `limit order book`, `OHLCV`, and others.

Happy data exploration!

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Import API into Postman](/market-data/how-to-guides/import-api-into-postman)[Next

Real-time data visualization with javascript](/market-data/how-to-guides/real-time-data-visualization-with-javascript)

* [Introduction](/market-data/how-to-guides/import-data-to-google-sheets-excel#introduction)
* [Getting started](/market-data/how-to-guides/import-data-to-google-sheets-excel#getting-started)
* [Retrieve BTC Exchange Rates in .csv format via web browser](/market-data/how-to-guides/import-data-to-google-sheets-excel#retrieve-btc-exchange-rates-in-csv-format-via-web-browser)
* [CSV import: Microsoft Excel](/market-data/how-to-guides/import-data-to-google-sheets-excel#csv-import-microsoft-excel)
* [CSV import: Google Sheets](/market-data/how-to-guides/import-data-to-google-sheets-excel#csv-import-google-sheets)
* [Summary](/market-data/how-to-guides/import-data-to-google-sheets-excel#summary)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.