CoinAPI.io Blog - What Kind of Crypto Data Can You Access Through API?

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

August 19, 2024

What Kind of Crypto Data Can You Access Through API?
====================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb6c9ef66dad546941d1cdd0e7131d9541fcf780d-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

Looking for different types of aggregated and standardized data from multiple cryptocurrency exchanges? You have come to the right place! This article will tell you what kind of data you can get with an easy API connection with our [Market Data API.](https://www.coinapi.io/market-data-api)

What you gain
-------------

By integrating with CoinAPI, **you access +350 cryptocurrency exchanges and obtain real-time and historical data. Some date back to 2011** (the exact depth can vary depending on the specific data type and exchange). We offer data granularity ranging from 1 second to 5 years. This allows for detailed analysis and visualization of market data. Below you will find what crypto data you can access.

Trades (Transactions)
---------------------

CoinAPI provides comprehensive information about trades and transactions. Both terms are used to describe the exchange of assets between buyers and sellers on cryptocurrency exchanges. The data provided for trades and transactions includes:

1. **Trade Data** - This includes details such as the trade ID, timestamp, price, and volume of each trade.
2. **Historical Trades** - You can access historical trade data, which allows you to analyze past trading activity.
3. **Real-time Trades** - CoinAPI offers real-time trade data, enabling you to monitor current market activity as it happens.

```
1[
2    {
3        "symbol_id": "BINANCE_SPOT_BTC_USDT",
4        "time_exchange": "2024-01-01T00:00:00.000000Z",
5        "time_coinapi": "2024-01-01T00:00:00.0045420Z",
6        "uuid": "001e66b6-3ee2-4a31-8d02-091780c044a2",
7        "price": 42283.58,
8        "size": 0.00069,
9        "taker_side": "SELL",
10        "id_trade": "3344747379",
11        "id_order_maker": "96bd6411-0005-0000-0000-000000000000",
12        "id_order_taker": "96bd6559-0005-0000-0000-000000000000"
13    },
14    {
15        "symbol_id": "BINANCE_SPOT_BTC_USDT",
16        "time_exchange": "2024-01-01T00:00:00.0010000Z",
17        "time_coinapi": "2024-01-01T00:00:00.0045353Z",
18        "uuid": "acd32990-8d34-41e1-a386-38216c15cea2",
19        "price": 42283.59,
20        "size": 0.00144,
21        "taker_side": "BUY",
22        "id_trade": "3344747380",
23        "id_order_maker": "96bd64ab-0005-0000-0000-000000000000",
24        "id_order_taker": "96bd655a-0005-0000-0000-000000000000"
25    },
26    {
27        "symbol_id": "BINANCE_SPOT_BTC_USDT",
28        "time_exchange": "2024-01-01T00:00:00.0030002Z",
29        "time_coinapi": "2024-01-01T00:00:00.0069037Z",
30        "uuid": "6e98275b-b7be-49d4-a697-9e4c2413e5fb",
31        "price": 42283.58,
32        "size": 0.00069,
33        "taker_side": "SELL",
34        "id_trade": "3344747381",
35        "id_order_maker": "96bd6411-0005-0000-0000-000000000000",
36        "id_order_taker": "96bd655b-0005-0000-0000-000000000000"
37    }
38]
```

*Trades example for BINANCE\_SPOT\_BTC\_USDT*

This data not only serves traders but also financial analysts, academic researchers, developers, and data scientists.

Exchange rates
--------------

This is the value at which one currency can be exchanged for another. It serves as a measure of the value of one currency relative to another. By connecting with CoinAPI, you will be able to learn the exchange rating of multiple cryptocurrencies on more than 350 exchanges. The minimal latency guaranteed by the connection via our API means that this data can be used, for example, in [statistical arbitrage](https://www.coinapi.io/blog/3-statistical-arbitrage-strategies-in-crypto).

```
1{
2    "time": "2024-08-20T08:37:56.0000000Z",
3    "asset_id_base": "BTC",
4    "asset_id_quote": "USD",
5    "rate": 60769.259091524554011334614945
6}
```

*Exchange rate for BTC/USD*

Read the full guide on [cryptocurrency exchange rates](https://www.coinapi.io/blog/cryptocurrency-exchange-rates).

Find out why is the role of [latency in cryptocurrency data](https://www.coinapi.io/blog/importance-of-low-latency-in-cryptocurrency-trading) crucial.

Quotes - snapshots of current trading information
-------------------------------------------------

Quotes provide trading information for assets, offering critical data for buyers and sellers to swiftly make informed decisions. Specifically, quotes display the best bid and ask prices for a particular trading pair on an exchange, serving as a **key indicator of current market conditions and the spread between buy and sell orders.** This data is also referred to as passive level 1 data.

Here are some key components of quotes in the Market Data API:

1. **Best Bid and Ask Prices** -Quotes provide information about the highest price a buyer is willing to pay (bid) and the lowest price a seller is willing to accept (ask) for a specific trading pair.
2. **Volume Information** - Along with the prices, quotes also include the volume resting on the best bid and ask. If the volume is zero, it indicates that the size is unknown.
3. **Timestamps** -Quotes include timestamps for when the quote was received by the exchange (time\_exchange) and when it was received by CoinAPI (time\_coinapi).

```
1[
2    {
3        "symbol_id": "BINANCE_SPOT_BTC_USDT",
4        "time_exchange": "2024-01-01T00:00:00.0227853Z",
5        "time_coinapi": "2024-01-01T00:00:00.0227853Z",
6        "ask_price": 42283.59,
7        "ask_size": 2.81993,
8        "bid_price": 42283.58,
9        "bid_size": 9.09329
10    },
11    {
12        "symbol_id": "BINANCE_SPOT_BTC_USDT",
13        "time_exchange": "2024-01-01T00:00:00.0333546Z",
14        "time_coinapi": "2024-01-01T00:00:00.0333546Z",
15        "ask_price": 42283.59,
16        "ask_size": 2.81861,
17        "bid_price": 42283.58,
18        "bid_size": 9.09329
19    },
20    {
21        "symbol_id": "BINANCE_SPOT_BTC_USDT",
22        "time_exchange": "2024-01-01T00:00:00.0384892Z",
23        "time_coinapi": "2024-01-01T00:00:00.0384892Z",
24        "ask_price": 42283.59,
25        "ask_size": 2.81861,
26        "bid_price": 42283.58,
27        "bid_size": 9.09277
28    },
29    {
30        "symbol_id": "BINANCE_SPOT_BTC_USDT",
31        "time_exchange": "2024-01-01T00:00:00.0384961Z",
32        "time_coinapi": "2024-01-01T00:00:00.0384961Z",
33        "ask_price": 42283.59,
34        "ask_size": 2.81861,
35        "bid_price": 42283.58,
36        "bid_size": 9.09159
37    }
38]
```

*Quotes for BINANCE\_SPOT\_BTC\_USDT*

For more detailed information, you can refer to the CoinAPI documentation on quotes:

<https://docs.coinapi.io/market-data/rest-api/quotes>

Order book data
---------------

An order book is a real-time updated list of buy and sell orders on a trading platform for a financial instrument (like cryptocurrencies), showing the quantity of the instrument being bid or offered at various price levels. Provides valuable clues as to whether prices are about to rise or fall.

### Order book - Level 1, Level 2, Level 3

CoinAPI delivers full-depth order book data:

1. **Level 1 (L1)** - Provides the best bid and ask prices along with their sizes. This is the most basic level of order book data and is often used for quick reference to the current market price.
2. **Level 2 (L2)** - Includes multiple price levels on both the bid and ask sides. It provides more depth than L1, showing the market depth beyond the best bid and ask prices. This level is useful for understanding the supply and demand at different price levels.
3. **Level 3 (L3)** - Offers the most granular view of the order book, including individual orders. It provides detailed information about each order, such as order ID, price, size, and the type of update (e.g., add, update, delete). This level is essential for high-frequency trading and in-depth market analysis.

```
1{
2  "symbol_id": "BINANCE SPOT BTC USDT",
3  "time_exchange": "2024-08-20T08:40:45.208000000Z",
4  "time_coinapi": "2024-08-20T08:40:45.213103Z",
5  "asks": [
6    {
7      "price": 60782.32000000,
8      "size": 1.04093000
9    },
10    {
11      "price": 60782.33000000,
12      "size": 0.00147000
13    },
14    {
15      "price": 60782.45000000,
16      "size": 0.00009000
17    },
18    {
19      "price": 60782.46000000,
20      "size": 0.03877000
21    },
22    {
23      "price": 60782.47000000,
24      "size": 0.00616000
25    },
26    {
27      "price": 60782.59000000,
28      "size": 0.00096000
29    },
30    {
31      "price": 60782.60000000,
32      "size": 0.09865000
33    },
34    {
35      "price": 60782.64000000,
36      "size": 0.00087000
37    },
38    {
39      "price": 60782.72000000,
40      "size": 0.00009000
41    },
42    {
43      "price": 60782.81000000,
44      "size": 0.00086000
45    },
46    {
47      "price": 60782.85000000,
48      "size": 0.00107000
49    },
50    {
51      "price": 60783.34000000,
52      "size": 0.00633000
53    },
54    {
55      "price": 60783.57000000,
56      "size": 0.32092000
57    },
58    {
59      "price": 60784.00000000,
60      "size": 0.04127000
61    },
62    {
63      "price": 60785.89000000,
64      "size": 0.10937000
65    }
66  ]
67}
```

*Orderbooks L3 for BINANCE\_SPOT\_BTC\_USDT*

### Order book snapshots

Order book snapshots provide a complete view of the order book at a specific point in time. They capture the state of the order book, including all the bids and asks, and are useful for getting a comprehensive picture of market depth. CoinAPI offers various levels of order book snapshots:

* **Book 5:** Top 5 levels from each side of the book.
* **Book 20:** Top 20 levels from each side of the book.
* **Book 50:** Top 50 levels from each side of the book.

The frequency of order book snapshots can vary, but CoinAPI aims to provide real-time updates with minimal latency.

OHLCV
-----

**OHLCV (Open, High, Low, Close, Volume) is a summary of changes in the price of a trading instrument and trading activity over a specified period.** The Open and Closed values indicate the price at which the security was first traded and the last price at the end of the period, respectively. The High and Low values represent the maximum and minimum prices during the period. The volume shows the total volume traded. OHLCV gives a detailed insight into price changes and the number of transactions that took place over a certain time. This data is available in various granularities, from 1 second to 5 years.

```
1[
2  {
3    "time_period_start": "2024-01-01T00:00:00.000000Z",
4    "time_period_end": "2024-01-02T00:00:00.000000Z",
5    "time_open": "2024-01-01T00:00:00.000000Z",
6    "time_close": "2024-01-01T23:59:59.999999Z",
7    "price_open": 42283.58,
8    "price_high": 44184.1,
9    "price_low": 42100.77,
10    "price_close": 44179.55,
11    "volume_traded": 26187.108389999987,
12    "trades_count": 1070662
13  },
14  {
15    "time_period_start": "2024-01-02T00:00:00.000000Z",
16    "time_period_end": "2024-01-03T00:00:00.000000Z",
17    "time_open": "2024-01-02T00:00:00.000000Z",
18    "time_close": "2024-01-02T23:59:59.999999Z",
19    "price_open": 44179.55,
20    "price_high": 45879.63,
21    "price_low": 44148.34,
22    "price_close": 44946.91,
23    "volume_traded": 62156.20929000035,
24    "trades_count": 2151078
25  },
26  {
27    "time_period_start": "2024-01-03T00:00:00.000000Z",
28    "time_period_end": "2024-01-04T00:00:00.000000Z",
29    "time_open": "2024-01-03T00:00:00.000000Z",
30    "time_close": "2024-01-03T23:59:59.999999Z",
31    "price_open": 44946.91,
32    "price_high": 45600,
33    "price_low": 40750,
34    "price_close": 42845.23,
35    "volume_traded": 81194.36704000004,
36    "trades_count": 2658036
37  },
38  {
39    "time_period_start": "2024-01-04T00:00:00.000000Z",
40    "time_period_end": "2024-01-05T00:00:00.000000Z",
41    "time_open": "2024-01-04T00:00:00.000000Z",
42    "time_close": "2024-01-04T23:59:59.999999Z",
43    "price_open": 42845.23,
44    "price_high": 44729.88,
45    "price_low": 42613.77,
46    "price_close": 44151.1,
47    "volume_traded": 48038.06097000002,
48    "trades_count": 1819941
49  },
50  {
51    "time_period_start": "2024-01-05T00:00:00.000000Z",
52    "time_period_end": "2024-01-06T00:00:00.000000Z",
53    "time_open": "2024-01-05T00:00:00.000000Z",
54    "time_close": "2024-01-05T23:59:59.999999Z",
55    "price_open": 44151.1,
56    "price_high": 44357.46,
57    "price_low": 42450,
58    "price_close": 44145.12,
59    "volume_traded": 40086.37648000012,
60    "trades_count": 2064843
61  }
62]
```

*This data structure contains daily trading information, including opening and closing times, price ranges (open, high, low, close), trading volume, and the number of trades for each day from January 1st to January 5th, 2024.*

Read more about [OHLCV](https://www.coinapi.io/blog/understanding-ohlcv-in-market-data-analysis) data or check in [doumentation](https://docs.coinapi.io/market-data/rest-api/ohlcv).

What’s more?
------------

In addition to those mentioned above, CoinAPI also provides data of varying levels of detail needed to better understand the crypto market.

### Metadata

Metadata in CoinAPI provides essential information about exchanges, assets, and symbols. This includes details such as the name of the exchange, the type of asset (e.g., cryptocurrency, fiat), and the specific symbols used for trading pairs. Metadata is crucial for understanding the context of the data you are working with, ensuring that you can accurately interpret and utilize the information provided by CoinAPI. It helps in mapping and standardizing data across different exchanges, making it easier to integrate and analyze.

### Raw Data

Raw data represents the most granular level of market information available. Unlike aggregated data types, raw data captures every single market event as it happens, without any summarization or aggregation. This includes individual trades, order book updates, and quote changes. Raw data is disseminated continuously, ensuring that users have access to the most immediate and detailed market insights. This type of data is particularly valuable for custom analysis, developing unique trading algorithms, and conducting in-depth market research.

### Tick-by-Tick Data

Tick-by-tick data is a subset of raw data that provides a detailed record of every single trade and quote update in the market. **Each "tick" represents a single event, such as a trade execution or a change in the best bid or ask price.** This data is invaluable for [high-frequency trading strategies](https://www.coinapi.io/blog/high-frequency-treading-strategies-in-crypto), quantitative analysis, and backtesting trading models. CoinAPI offers access to historical tick-by-tick data through flat files, allowing users to perform comprehensive historical analysis and develop data-driven trading strategies.

Get to know [Market Data API](https://www.coinapi.io/market-data-api) better.

Something new: crypto indexes
-----------------------------

In addition to the above data available through the Market Data API, you can now also collect information on crypto indices thanks to [Indexes API.](https://www.coinapi.io/indexes-api) Crypto indexes, such as those provided by CoinAPI, are typically calculated by **tracking a selection of cryptocurrencies based on specific criteria**, such as market capitalization. The index value is derived from the prices of the included cryptocurrencies, which are weighted according to their market cap or other factors. This allows the index to **reflect the overall performance of the cryptocurrency market or its segment.**

Read: [Crypto Indexes - Everything You Need to Know](https://www.coinapi.io/blog/crypto-indexes-everything-you-need-to-know)

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