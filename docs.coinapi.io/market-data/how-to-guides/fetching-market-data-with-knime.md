Fetching market data with KNIME | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/fetching-market-data-with-knime)

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
* Fetching market data with KNIME

On this page

Fetching market data with KNIME
===============================

Introduction[​](/market-data/how-to-guides/fetching-market-data-with-knime#introduction "Direct link to Introduction")
----------------------------------------------------------------------------------------------------------------------

[KNIME](https://www.knime.com/) is an excellent tool for data analytics and integration, offering a user-friendly, node-based interface to design and automate data workflows.

Its capabilities encompass data `preprocessing`, `transformation`, `analysis`, `machine learning`, and `visualization`, making it versatile for a wide range of data-related tasks.

By seamlessly integrating with our `REST API`, you gain the ability to fetch comprehensive market data, providing you with the power to conduct in-depth research,
formulate effective trading strategies, manage portfolios, and make informed, data-driven decisions in the dynamic cryptocurrency market.

Prerequisites[​](/market-data/how-to-guides/fetching-market-data-with-knime#prerequisites "Direct link to Prerequisites")
-------------------------------------------------------------------------------------------------------------------------

* A CoinAPI key (obtainable by signing up on the CoinAPI website)
* Installed [KNIME Analytics Platform](https://www.knime.com/knime-analytics-platform)

Creating KNIME workflow to get BTC exchange rates[​](/market-data/how-to-guides/fetching-market-data-with-knime#creating-knime-workflow-to-get-btc-exchange-rates "Direct link to Creating KNIME workflow to get BTC exchange rates")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

If you have properly installed KNIME on your computer and obtained the CoinAPI key, we can start by preparing a `workflow`.

`Workflow` refers to the visual representation of a data analysis process.   
It typically consists of nodes (also known as steps or tasks) connected in a specific sequence,
where each node performs a specific operation on the data.

Here's an example of two nodes connected:

1. `Get Request` (sends an HTTP GET request to a specified URL, typically an API endpoint like `rest.coinapi.io/v1/exchangerate/BTC`)
2. `Output JSON` (receives the JSON data obtained from the API response and presents it in a structured format)

Using this example, you can download data and view it within the `Output JSON` block.

![KNIME exchange rates](/assets/images/knime-1-get-exchange-rates-966db5f252665a109666380ba0afe318.jpg)

Each node result may be easily **previewed**:

![KNIME preview](/assets/images/knime-2-first-preview-01557cf1d7b71d7aca6fbe5687c25e6d.jpg)

Here's an output of the `Get Request` node:

![KNIME preview - get request node](/assets/images/knime-3-preview-d60bddbc66a74df1512fe9e66fda6bb3.jpg)

Here's an output of the `Output JSON` node:

![KNIME preview - output json node](/assets/images/knime-4-preview-73aebb3133cb63a43db8037ac6fff739.jpg)

Configuring GET Request in KNIME[​](/market-data/how-to-guides/fetching-market-data-with-knime#configuring-get-request-in-knime "Direct link to Configuring GET Request in KNIME")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

To configure a `GET Request` block, click `Configure`:

![Configuring block](/assets/images/knime-5-click-configure-13e444a5448302f18fd8ea3d93ba5328.jpg)

In the `Connection Settings` tab, enter the URL of the resource you want to retrieve, e.g `https://rest.coinapi.io/v1/exchangerate/BTC`:

![Configuring Get Request block - url](/assets/images/knime-6-configure-url-2d9ac51970acd434a6b57510926203ef.jpg)

In the `Request Headers` tab, enter the `X-CoinAPI-Key` header with the API key you have obtained via the website.

![Configuring Get Request block - auth header](/assets/images/knime-7-configure-auth-header-89a1f90b661c365497bcc61f882f53cc.jpg)

Summary[​](/market-data/how-to-guides/fetching-market-data-with-knime#summary "Direct link to Summary")
-------------------------------------------------------------------------------------------------------

Simple but also more complex workflows can be designed, enabling advanced operations like filtering, grouping, and utilizing your own Python scripts, culminating in the option
to save the processed data in various formats such as CSV, Excel, or others.

`KNIME` together with our `Market Data API` allows users to analyze market finance data for tasks like machine learning, data analysis, generating charts, optimizing portfolios, managing risks, backtesting trading strategies, and more.

![Configuring Get Request block - auth header](/assets/images/knime-8-order-book-2f5300dc7230b96b7118ddbf3edf1fe5.jpg)

Embrace the world of market data analysis!

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Creating a historical crypto price chart using CoinAPI and D3.js](/market-data/how-to-guides/creating-historical-crypto-price-chart-using-CoinAPI-and-D3-js)[Next

Get Historical OHLCV Data Using CoinAPI](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi)

* [Introduction](/market-data/how-to-guides/fetching-market-data-with-knime#introduction)
* [Prerequisites](/market-data/how-to-guides/fetching-market-data-with-knime#prerequisites)
* [Creating KNIME workflow to get BTC exchange rates](/market-data/how-to-guides/fetching-market-data-with-knime#creating-knime-workflow-to-get-btc-exchange-rates)
* [Configuring GET Request in KNIME](/market-data/how-to-guides/fetching-market-data-with-knime#configuring-get-request-in-knime)
* [Summary](/market-data/how-to-guides/fetching-market-data-with-knime#summary)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.