CoinAPI.io Blog - Create Python Cryptocurrency Charts with CoinAPI

**🚀 Metrics API V2 Live:**

Complete Market Intelligence - CEX + DeFi Data in One API

[Learn More](https://www.coinapi.io/blog/metrics-api-v2-trading-volume-analysis-and-on-chain-metrics)

[![background](https://cdn.sanity.io/images/o65xz72l/production/268144c90959611dea3e360f81e4549c3cd03fd0-142x34.svg)![background](https://cdn.sanity.io/images/o65xz72l/production/e0ca0c29b08cb53631d77de4a84246da316d55d2-142x34.svg)](/)

* Products
* Use Cases
* Pricing
* Developers
* Resources
* Contact us
* [Log in](https://console.coinapi.io/)

May 17, 2023

Create Python Cryptocurrency Charts with CoinAPI
================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ffacd4f60a668a4a3463c255e1f3428c9eb3c9623-1200x802.png%3Frect%3D0%2C140%2C1200%2C522%26w%3D920%26h%3D400&w=1920&q=75)

Create Python Cryptocurrency Charts with CoinAPI
================================================

***Here’s a step-by-step guide to creating a [Python](https://www.python.org/) library that provides a lightweight and interactive charting solution for data visualization using [CoinAPI](https://www.coinapi.io/blog/what-is-coinapi-the-evolution-of-free-cyrpto-api) data, showcasing Python as a versatile programming language. This tutorial is dedicated to developers who want to build interactive cryptocurrency charts with Python and [CoinAPI](https://www.coinapi.io/market-data-api).***

Introduction to Algorithmic Trading
-----------------------------------

Algorithmic trading is a method of [executing trades](https://www.coinapi.io/learn/glossary/trade-execution) using pre-programmed instructions, known as algorithms. These algorithms analyze market data, identify patterns, and make trades based on predefined rules. In the fast-paced world of cryptocurrency trading, algorithmic trading has gained significant popularity due to its ability to execute trades quickly and efficiently.

By leveraging algorithms, traders can capitalize on market opportunities that might be missed by manual trading. This section will introduce you to the basics of algorithmic trading and its applications in the cryptocurrency market, providing a foundation for building your own trading algorithms and understanding the crypto market.

Step 1: Set Up Your Project and API Key
---------------------------------------

Start by setting up a new Python project. Create a directory for your library and navigate to it in your terminal or command prompt.

**Step 2: Install Dependencies**
--------------------------------

To begin, you’ll need to install the necessary dependencies. You should also install the ccxt library, which is designed for connecting to and trading on various cryptocurrency exchanges.

In this case, you’ll need requests for making HTTP requests and a charting library such as Plotly or Matplotlib for data visualization. Install them using pip: 1 pip install requests plotly ccxt

Step 3: Create the CoinAPI Wrapper for Historical Price Data
------------------------------------------------------------

Next, create a file named [coinapi.py](http://coinapi.py) and define a class called CoinAPI that will serve as the wrapper for CoinAPI’s RESTful API. Import the required modules:

```
1import requests
2class CoinAPI:
3  def __init__(self, api_key):
4    self.api_key = api_key
5    self.base_url = 'https://rest.coinapi.io/v1/'
```

In the CoinAPI class, define methods for accessing the CoinAPI endpoints to fetch the desired [cryptocurrency data](https://www.coinapi.io/blog/how-to-get-historical-and-real-time-crypto-data). For example, you can create a method to retrieve the historical prices of a specific cryptocurrency:

```
1def get_historical_prices(self, symbol, start_date, end_date):
2    url = f"{self.base_url}ohlcv/{symbol}/USD/history?period_id=1DAY&time_start={start_date}&time_end={end_date}"
3    headers = {'X-CoinAPI-Key': self.api_key}
4
5    response = requests.get(url, headers=headers)
6    data = response.json()
7
8    return data
```

This example uses the requests library to make an HTTP GET request to the CoinAPI endpoint and retrieves the historical price data for a specific cryptocurrency symbol ([symbol](https://docs.coinapi.io/market-data/rest-api/metadata/list-all-symbols)) within a given date range (start\_date and end\_date). Additionally, you can track and analyze data from multiple cryptocurrencies to gain a comprehensive view of the market.

Step 4: Implement Data Visualization
------------------------------------

Create a separate file named [charting.py](http://charting.py) to handle the chart generation. Import the necessary charting library:

```
1import plotly.graph_objects as go
```

Define a function that takes the fetched [cryptocurrency data](https://www.coinapi.io/) and generates an interactive chart. Here’s an example using Plotly:

```
1def generate_chart(data):
2    x = [entry['time_period_start'] for entry in data]
3    y = [entry['price_close'] for entry in data]
4
5    fig = go.Figure(data=go.Scatter(x=x, y=y))
6    fig.update_layout(title='Historical Prices', xaxis_title='Date', yaxis_title='Price')
7    fig.show()
```

This function takes the fetched data and extracts the relevant [data points](https://www.coinapi.io/learn/glossary/data-points), such as the timestamp (time\_period\_start) and the closing price (price\_close).

It then uses Plotly to create a line chart, setting the appropriate x-axis and y-axis labels. Advanced charting techniques like these are essential for developing a robust trading algorithm.

### Advanced Charting Techniques

Advanced charting techniques can help you gain deeper insights into [cryptocurrency markets and make](https://www.coinapi.io/blog/market-making-in-crypto) more informed trading decisions. One such technique is the use of technical indicators, which can be applied to historical price data to identify trends and patterns. Some popular technical indicators include moving averages, relative strength index (RSI), and Bollinger Bands.

Another advanced charting technique is the use of candlestick charts, which provide a more detailed view of price movements than traditional line charts. Candlestick charts show the open, high, low, and closing price of a cryptocurrency over a specific period, allowing you to analyze market sentiment and volatility.

You can also use advanced charting libraries like Plotly to create interactive and dynamic charts that can be customized to suit your needs. Plotly allows you to create a wide range of charts, including line charts, bar charts, and scatter plots, and also provides tools for adding technical indicators and other features to your charts.

**Step 5: Put It All Together**
-------------------------------

Create a [main.py](http://main.py) file to demonstrate the usage of your library. In this file, import both the coinapi and charting modules:

```
1from coinapi import CoinAPI
2import charting
```

Instantiate the CoinAPI class by providing your CoinAPI key:

```
1api_key = 'YOUR_API_KEY'
2coin_api = CoinAPI(api_key)
```

Fetch the desired cryptocurrency data using the get\_historical\_prices method:

```
1symbol = 'BTC'
2start_date = '2022-01-01T00:00:00'
3end_date = '2022-01-31T23:59:59'
4data = coin_api.get_historical_prices(symbol,
```

You can also explore various APIs and experiment with additional features to customize and improve your cryptocurrency charts. Staying informed with market data and trends is crucial for making the most out of these tools and strategies.

Cryptocurrency Data Charts with Python and CoinAPI
--------------------------------------------------

Here’s an example of how you can use the library to fetch historical price data from CoinAPI and generate a chart using Plotly:

```
1from coinapi import CoinAPI
2import charting
3
4# Instantiate the CoinAPI class
5api_key = 'YOUR_API_KEY'
6coin_api = CoinAPI(api_key)
7
8# Fetch historical price data for Bitcoin (BTC)
9symbol = 'BTC'
10start_date = '2022-01-01T00:00:00'
11end_date = '2022-01-31T23:59:59'
12data = coin_api.get_historical_prices(symbol, start_date, end_date)
13
14# Generate a chart using Plotly
15charting.generate_chart(data)
```

In the above example, you import the CoinAPI class and the charting module. After instantiating the CoinAPI class with your API key, you call the get\_historical\_prices method to fetch the [historical price data for Bitcoin](https://www.coinapi.io/blog/a-guide-to-using-cryptotick-for-crypto-historical-data) (BTC) within a specified date range.

Once you have the data, you can pass it to the generate\_chart function from the charting module to generate an interactive chart using Plotly.

Remember to replace ‘`YOUR_API_KEY`’ with your actual [CoinAPI key](https://www.coinapi.io/market-data-api/pricing). Have a look at our [documentation](https://docs.coinapi.io/) for more instructions.

This example demonstrates a basic usage scenario, and you can further customize the chart by exploring the features and options provided by the Plotly library. This example demonstrates how Python, as a versatile programming language, can be used to create powerful and interactive cryptocurrency charts.

#### More to read:

[**How to deploy a currency alerting pipeline with Quix and CoinAPI**](https://www.coinapi.io/blog/deploy-real-time-currency-alerting-pipeline)

[**What’s better: building API or buying one?**](https://www.coinapi.io/blog/whats-better-building-api-or-buying-one)

![background](https://cdn.sanity.io/images/o65xz72l/production/e8a6b2e74f8d4106aca6ea9739a663190aadf694-40x40.svg)

Stay up-to-date with the latest CoinApi News.

Send

By subscribing to our newsletter, you accept our website terms and privacy policy.

### Recent Articles

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F1c608fa1f94b18e18e30a04e3006c5455b4dfeca-1000x500.png&w=3840&q=75)

Product Features

How to Get Accurate Historical Token Price Data for Financial Reporting

Retrieve complete, audit-ready historical token price data with CoinAPI. Perfect for finance managers, controllers, and ops teams handling Web3 assets.](/blog/historical-token-price-data-financial-reporting)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fabe93ecc9d8dfb15701c7ab459b916701aaf13e1-1000x500.png&w=3840&q=75)

Crypto Knowledge

Spot Trading in Crypto: What It Is, How It Works, and How to Master It

Learn spot trading in crypto from basics to pro strategies. Understand bids, asks, order books & use CoinAPI’s real-time and historical data.](/blog/spot-trading-in-crypto-guide)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ffee6e77e8c599cbdc3e536317ac7adcbbbb59f5e-1000x500.png&w=3840&q=75)

Crypto Knowledge

Understanding Crypto Market Data: From Tick Trades to OHLCV and Order Books

Choose the right crypto market data type - tick trades, quotes, order books, or OHLCV—for trading success. Complete guide with examples and use cases. Focus keyphrase: crypto market data](/blog/understanding-crypto-market-data-tick-trades-ohlcv-order-books)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F8c92ab519a2ec5af8b7edc3ba2371d9243750cc7-1000x500.png&w=3840&q=75)

Product Features

Crypto Tax Made Simple: How CoinAPI Exchange Rates Power Accurate Accounting

Solve crypto tax compliance with professional exchange rates API. Get audit-ready historical pricing, eliminate capital gains errors, and standardize crypto pricing across exchanges.](/blog/crypto-tax-coinapi-exchange-rates)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fa7ddd03200081ffce3dfdd9d9bc805c4cbac5801-1000x500.png&w=3840&q=75)

Crypto Knowledge

What Everyone Gets Wrong About L3 Data in Crypto

L3 data in crypto gives you full visibility into every individual order — but most traders use it wrong. Learn how to read L3 correctly, avoid common pitfalls, and scale smarter with CoinAPI.](/blog/what-everyone-gets-wrong-about-l3-data-in-crypto)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fab2a315d6528b49cda3fd200b418af97ce48894f-1000x500.png&w=3840&q=75)

Crypto Knowledge

How Level 3 Market Data Transforms Trading Performance

What if you could see every individual order placement, modification, and cancellation happening in real-time across crypto exchanges? Most traders operate blindfolded with basic price feeds, while sophisticated institutions access Level 3 market data—granular, order-by-order intelligence that reveals market microstructure 99% of traders never see.](/blog/how-level-3-market-data-transforms-trading-performance)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F47694398be69f125e8bc4fcd68c23cba8ad4f7e2-1000x500.png&w=3840&q=75)

Product Features

Pros and Cons of JSON-RPC and REST APIs Protocols

Choose the right API protocol for crypto trading. Compare JSON-RPC vs REST for market data, trading bots, and DeFi applications with real performance benchmarks.](/blog/pros-and-cons-of-json-rpc-and-rest-apis-protocols)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ff4583e287f8949afaddc3a4aaf89091f834a8bd6-1000x500.png&w=3840&q=75)

Use case

Exchange Rates API for Fast Historical Token Prices

Exchange rates API for finance managers at Web3 companies. Get fast historical closing prices, multiple symbols per call, and ISO timestamps for compliance.](/blog/exchange-rates-api-for-fast-historical-token-prices)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fecfd635f082d4e6a312b9312725cf195c5d9dccd-1000x500.png&w=3840&q=75)

Crypto Knowledge

Why Crypto to Fiat APIs Are Revolutionizing Financial Operations

Discover how crypto-to-fiat APIs solve critical business challenges in portfolio management, tax compliance, and financial reporting. Learn why leading finance teams are standardizing on professional-grade solutions.](/blog/why-crypto-to-fiat-apis-are-revolutionizing-financial-operations)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fe7526651c2ce24101581e90a5982c62bb1b84f18-1000x500.png&w=3840&q=75)

Product Features

Metrics API V2: Trading Volume Analysis and On-Chain Metrics

Most crypto APIs show you prices on exchanges. But that’s only half the story. CoinAPI’s new Metrics API V2 gives you real-time visibility into DeFi protocols, stablecoin flows, and cross-chain activity — the $200B+ blind spot in traditional market data. With sub-30 second updates, standardized metrics, and multi-chain coverage, it's the fastest way to unlock on-chain trading signals, measure TVL, and track stablecoin health. If you’re still trading without it, you're flying blind.](/blog/metrics-api-v2-trading-volume-analysis-and-on-chain-metrics)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb5471406ca9cbf8f906574131747c4233f29e240-1000x500.png&w=3840&q=75)

Product Features

Crypto Data Download: The Flat Files Advantage

Discover how to download crypto data for free and access premium bulk historical datasets. Compare APIs, learn S3 methods, and start backtesting with terabytes of clean cryptocurrency market data.](/blog/crypto-data-download-the-flat-files-advantage)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fca54fa639768f18864c62215de750ec797f31ddd-1000x500.png&w=3840&q=75)

Product Features

Why WebSocket Multiple Updates Beat REST APIs for Real-Time Crypto Trading

Learn why WebSocket multiple updates for crypto trading APIs provide faster signals than single response data. Discover real-time OHLCV implementation strategies for Bitcoin and cryptocurrency market data.](/blog/why-websocket-multiple-updates-beat-rest-apis-for-real-time-crypto-trading)

### Crypto API made simple: Try now or speak to our sales team

[Start for Free](/market-data-api/pricing)[Get in Touch](/contact-us)

[![background](https://cdn.sanity.io/images/o65xz72l/production/99475f0760777c30125556b2707e1e8f77f2fba0-179x42.svg)](/)

###### Join our newsletter

* [![X](https://cdn.sanity.io/images/o65xz72l/production/89a93ecdd3eaa62f0d2bad091ff6d92a31e9c372-28x28.svg)](https://twitter.com/realcoinapi "X")
* [![Linkedin](https://cdn.sanity.io/images/o65xz72l/production/be666e8656abe83e43c1db9a3ab76d44b9af5cb5-28x28.svg)](https://www.linkedin.com/company/coinapi "Linkedin")
* [![Github](https://cdn.sanity.io/images/o65xz72l/production/80703d2d9baaef7e7f5471a54a720b9383a63aab-28x28.svg)](https://github.com/coinapi/coinapi-sdk "Github")
* [![T.me](https://cdn.sanity.io/images/o65xz72l/production/39be23a1db383ad12c3e9d4bebae9bc77bf59b8b-28x28.svg)](https://t.me/coinapiofficial "T.me")
* [![Discord](https://cdn.sanity.io/images/o65xz72l/production/9862f060f9b89536f18d4e8770a11bfb00c3e3fd-30x28.svg)](https://discord.gg/vgJbjjsVaC "Discord")
* [![Reddit](https://cdn.sanity.io/images/o65xz72l/production/d02e41d1eab87d289f2bc6a390bcd0c7def1b7ac-30x28.svg)](https://www.reddit.com/r/CoinAPI/ "Reddit")
* [![YouTube](https://cdn.sanity.io/images/o65xz72l/production/535425f0f99df8b6173d663721f8941430d637b2-28x28.svg)](https://www.youtube.com/@CoinAPI_Official "YouTube")
* [![G2](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F4b1d455c2cab4bf625e7cc96a1b74695c0b3c4bc-28x28.png&w=64&q=75)](https://www.g2.com/products/coinapi/reviews "G2")

###### Products

###### Products

* [Market Data API](/products/market-data-api)
* [Indexes API](/products/indexes-api)
* [EMS Trading API](/products/ems-api)
* [Flat Files](/products/flat-files)
* [Exchange Rates API](/products/exchange-rates-api)
* [Exchange Link](https://www.coinapi.io/products/exchange-link)

###### CoinAPI.io

###### CoinAPI.io

* [Home](https://www.coinapi.io/)
* [API Docs](https://docs.coinapi.io/?_gl=1*jgom05*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Blog](https://www.coinapi.io/blog)

###### Help

###### Help

* [Contact sales](/contact-us)
* [Contact support](https://console.coinapi.io/?link=/support-tickets)
* [How-to Guides](https://docs.coinapi.io/market-data/how-to-guides/?_gl=1*16m3ndl*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [FAQ](https://docs.coinapi.io/general/faq/?_gl=1*dfjpiw*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Metadata Explorer](https://docs.coinapi.io/market-data/metadata-tables/introduction)

###### Developers

###### Developers

* [Helper Libraries](https://github.com/api-bricks/api-bricks-sdk/)
* [API Documentation](https://docs.coinapi.io/?_gl=1*iuavdb*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Status Page](https://status.coinapi.io/?_gl=1*1ww1bbe*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)

###### Legal

###### Legal

* [Terms of service](/legal#terms)
* [Acceptable Usage Policy](/legal#aup)
* [Privacy Policy](/legal#policy)

###### API Bricks brands

###### API Bricks brands

* [FinFeedAPI](https://finfeedapi.com/?utm_source=coinapi.io&utm_medium=referral&utm_campaign=footer)

![background](https://cdn.sanity.io/images/o65xz72l/production/5f005fa1cc9dc85c59ae054bb4a4838566b65c4e-25x26.svg)Copyright 2025 API BRICKS LTD F/K/A COINAPI LTD or its affiliates. All rights reserved.