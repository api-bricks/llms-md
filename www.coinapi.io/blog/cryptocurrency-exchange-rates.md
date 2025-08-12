CoinAPI.io Blog - Cryptocurrency exchange rates

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

May 23, 2024

Cryptocurrency exchange rates
=============================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F456bb7adb2224e16a74a82a0c3ef45cc8307493e-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

***In the traditional world of [fiat money](https://corporatefinanceinstitute.com/resources/economics/fiat-money-currency/), exchange rates are simply “the rates at which the money of one country can be changed for the money of another country”. However, in the world of cryptocurrencies, which no country officially controls or ties to itself, the definition needs some adjustment. Let’s break it down!***

What are crypto exchange rates?
-------------------------------

In the crypto context, an **exchange rate** can be explained as both:

**The value at which:**

* **One cryptocurrency can be exchanged for another – e.g. BTC to ETH**
* **A cryptocurrency can be exchanged for a fiat currency – e.g. SOL to USD**

In general, these rates are dynamic. They can change based on market supply and demand, similar to traditional currencies. Obviously, external factors like market sentiment, economic news, regulatory changes, technological developments, trends, and many others (e.g. Dogecoin’s rise after endorsement from Elon Musk) can cause these changes as well.

> *💡 An exchange rate is always a pair of assets e.g. BTC/SOL or ETH/EUR.*

What is the difference between the exchange rate and price in cryptocurrencies?
-------------------------------------------------------------------------------

People often use these terms interchangeably, which can confuse them.

### **Exchange rate**

The value of one (crypto)currency compared to another. Used in trading and converting assets. *For example, if the BTC/ETH exchange rate is 20, one Bitcoin can be exchanged for 20 ETH.*

### **Price**

The value of a single unit of a cryptocurrency in terms of fiat currency or another cryptocurrency. *For example, if Bitcoin is priced at $30,000, one Bitcoin is worth $30,000.*

Types of Crypto Exchange Rates
------------------------------

Different types of exchange rates exist based on asset pairs, timing, data sources, and calculation methods. Hence, when choosing an exchange rate platform, it’s essential to understand these differences.

### **Free-floating vs Fixed**

* **Free-floating exchange rate:** the value of a crypto dictated by market supply and demand without direct intervention of a central authority. Consequently, most cryptocurrencies operate like that.
  + *Example: [Bitcoin](https://bitcoin.org/) to US dollar (BTC/USD); [Ethereum](https://ethereum.org/en/) to Euro (ETH/EUR)*
* **Fixed exchange rate:** A fixed exchange rate, also known as a pegged exchange rate, is one where the value of a cryptocurrency is tied to another currency, commodity, or cryptocurrency. An example is Tether (USDT), which is pegged to the US Dollar, aiming to maintain a 1:1 value ratio.
  + *Example: [Tether](https://tether.to/en/) to US dollar (USDT/USD); [USD Coin](https://www.circle.com/en/usdc) to US dollar (USDC/USD)*

**Spot vs Forward value**

* **Spot rate (cash value):** The [spot rate](https://www.investopedia.com/terms/s/spotprice.asp) is the current market price at which a cryptocurrency can be bought or sold for immediate delivery. For instance, if you check the current price of Ethereum (ETH) on an exchange like Binance, that price is its spot rate.
  + *Example: Spot price of Bitcoin on an exchange*
* **Forward value rate:** The [forward rate](https://www.investopedia.com/ask/answers/042315/what-difference-between-forward-rate-and-spot-rate.asp) is an agreed-upon and predicted price for a cryptocurrency transaction that will occur at a future date. So, professionals often use forward contracts to hedge against price volatility. For example, a trader might agree to buy Bitcoin at a set price in three months to avoid potential price spikes.
  + *Example: Bitcoin forward futures contract*

### **Single vs Aggregated**

* **Single exchange rate:** This is the rate provided by a single exchange platform. The price might vary significantly between different platforms due to differences in supply and demand. For example, the price of Bitcoin on Coinbase might differ from its price on Kraken at any given time.
  + *Example: [Cardano](https://cardano.org/) price on [Coinbase](https://www.coinbase.com/pl/)*
* **Aggregated exchange rate:** An aggregated exchange rate combines prices from multiple exchanges to provide an average rate. This approach aims to give a more balanced and accurate view of the market. Services like CoinGecko or CoinAPI often use aggregated exchange rates to present a more comprehensive market price.
  + *Example: Bitcoin price via Market Data API; Ethereum aggregated price on [CoinMarketCap](https://coinmarketcap.com/)*

### **VWAP vs VWAP-24H vs Order book**

* **Volume-Weighted Average Price (VWAP):** It is a trading benchmark that gives the average price a cryptocurrency has traded at throughout the day, based on both volume and price. It provides traders with insight into the market trend and the average price they might expect to pay
  + *Example: Bitcoin VWAP on [Kraken](https://www.kraken.com/)*
* **Volume-Weighted Average Price 24H (VWAP-24H):** Similar to VWAP, but calculated over a 24-hour period. This gives a broader view of the average trading price over a full day, which is useful for traders looking to understand longer-term trends.
  + *Example: [Solana](https://solana.com/pl) VWAP-24H via Market Data API*
* **Order book analysis:** This involves examining the list of buy and sell orders on an exchange’s order book to understand market sentiment and liquidity. The order book can show where the majority of buy or sell orders are clustered, indicating potential support or resistance levels.
  + *Example: [Litecoin](https://litecoin.org/) order book on [Bitfinex](https://www.bitfinex.com/)*

How are exchange rates calculated?
----------------------------------

There are many ways an exchange or data source can estimate or calculate an exchange rate. Some people focus on the [Simple Moving Average (SMA)](https://www.fidelity.com/learning-center/trading-investing/technical-analysis/technical-indicator-guide/sma), or just the average or median value from a specific period.

One of the most common and reliable methods of exchange rate calculation is to use the `VWAP` ([Volume Weighted Average Price](https://www.investopedia.com/terms/v/vwap.asp)) over the last 24 hours, known as `VWAP-24H`.

Afterward, to make the method even more accurate the value should be calculated **based on the data from multiple exchanges** (aggregated data). Aggregated data gives us the overlook of the entire market, and eliminates potential errors that could occur on a single exchange.

### Example of **Volume-Weighted Average Price (VWAP) Calculation** calculation

Let’s imagine that this simple order book below represents real data that we’ll calculate right now.

#### **Buy Orders (Bids)**

* Price: $69,800 USD, Amount: 0.5 BTC
* Price: $69,850 USD, Amount: 0.7 BTC
* Price: $69,900 USD, Amount: 1.0 BTC

#### **Sell Orders (Asks)**

* Price: $70,000 USD, Amount: 0.3 BTC
* Price: $70,050 USD, Amount: 0.6 BTC
* Price: $70,100 USD, Amount: 0.8 BTC

We have three “Buy Orders” and the same amount of “Sell Orders”. Again it’s a simple example that shows the thought behind the equation. Usually, we have hundreds or thousands of records to calculate from.

![VWAP formula](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb6792d8b8d9875610fca0bb8630b2eee13326696-300x78.webp&w=1920&q=75)

*Source: Tradewell.app*

#### Step-by-step VWAP calculation

1. **The sum of (Price × Volume) for all trades:** First, we have to take all of the amounts sold (Volume) and multiply it by the price in USD.(69,800×0.5)+(69,850×0.7)+(69,900×1.0)+(70,000×0.3)+(70,050×0.6)+(70,100×0.8) = 34,900+48,895+69,900+21,000+42,030+56,080=272,805
2. **The sum of Volumes:** Then we just sum up the volumes.0.5+0.7+1.0+0.3+0.6+0.8=3.9
3. **VWAP Calculation**The only thing left is to take the sum of (Volume x Price) and divide it by Volume**VWAP=272,805/3.9=69,950**

So, the VWAP for BTC/USD is approximately **$69,950**

CoinAPI’s Market Data API
-------------------------

We base our exchange rate calculation on the `VWAP-24H` method, multiple data sources, and protocols (e.g. REST API and Websocket) to calculate the exchange rate, we carefully manage the data sources to have even higher-quality data. Basically, here’s how the algorithm works:

1. **Data Sources**: Only legitimate data from spot markets are used.
2. **Filtering**: Alghoritms discard data with large spreads or outdated quotes (over 5 minutes old)
3. **Price Calculation**: Midpoint prices from quotes are weighted by trade volumes.
4. **Regular Updates**: The VWAP is updated every second, and the 24-hour volume for each symbol is refreshed every 4 hours.
5. **Data Quality**: Market Data API includes only the highest-ranked exchanges and excludes outliers (3 sigma range) if enough data points exist.
6. **Final Rate**: A tree structure and our proprietary method finalize the exchange rates.

Additionally, our crypto exchange rates are accurately delivered data from many data sources. The goal behind creating such a feature was to eliminate the need to check the price on separate exchanges and have an aggregated and more resilient overlook of a crypto market.

### Examples of Market Data API’s exchange rate requests

#### **Get all current rates**

This request retrieves the current exchange rate between the requested asset and all other assets. It provides a snapshot of the market at a specific time, helping traders and investors understand the current value of their assets.

```
1{
2  "asset_id_base": "BTC",
3  "rates": [
4        {
5            "time": "2024-05-23T12:10:20.0000000Z",
6            "asset_id_quote": "USD",
7            "rate": 69981.772240612035520805593223
8        },
9        {
10            "time": "2024-05-23T12:10:20.0000000Z",
11            "asset_id_quote": "EUR",
12            "rate": 64477.807053889507677355109199
13        },
14    {
15        {
16            "time": "2024-05-23T12:10:20.0000000Z",
17            "asset_id_quote": "CNY",
18            "rate": 505596.2762323691855012123533
19        },
20        {
21            "time": "2024-05-23T12:10:20.0000000Z",
22            "asset_id_quote": "GBP",
23            "rate": 54899.932493658899152080312809
24        }
25  ]
26}
```

#### **Timeseries data**

This request provides historical exchange rates between two assets over time. It helps analyze trends, make informed trading decisions, and understand the historical performance of assets.

```
1[
2    {
3        "time_period_start": "2024-05-20T00:00:00.0000000Z",
4        "time_period_end": "2024-05-20T00:01:00.0000000Z",
5        "time_open": "2024-05-20T00:00:00.0000000Z",
6        "time_close": "2024-05-20T00:00:00.0000000Z",
7        "rate_open": 66266.8776650577,
8        "rate_high": 66266.8776650577,
9        "rate_low": 66266.8776650577,
10        "rate_close": 66266.8776650577
11    },
12    {
13        "time_period_start": "2024-05-20T00:01:00.0000000Z",
14        "time_period_end": "2024-05-20T00:02:00.0000000Z",
15        "time_open": "2024-05-20T00:01:00.0000000Z",
16        "time_close": "2024-05-20T00:01:00.0000000Z",
17        "rate_open": 66266.1186767057,
18        "rate_high": 66266.1186767057,
19        "rate_low": 66266.1186767057,
20        "rate_close": 66266.1186767057
21    },
22    {
23        "time_period_start": "2024-05-20T00:02:00.0000000Z",
24        "time_period_end": "2024-05-20T00:03:00.0000000Z",
25        "time_open": "2024-05-20T00:02:00.0000000Z",
26        "time_close": "2024-05-20T00:02:00.0000000Z",
27        "rate_open": 66254.1070498383,
28        "rate_high": 66254.1070498383,
29        "rate_low": 66254.1070498383,
30        "rate_close": 66254.1070498383
31    },
32  ]
33}
```

#### **Timeseries periods**

This request retrieves historical exchange rates for any asset pair, grouped into specific time periods. It is useful for backtesting trading strategies and analyzing asset performance over different intervals.

```
1[
2  {
3    "period_id": "1SEC",
4    "length_seconds": 1,
5    "length_months": 0,
6    "unit_count": 1,
7    "unit_name": "second",
8    "display_name": "1 Second"
9  },
10  {
11    "period_id": "30MIN",
12    "length_seconds": 1800,
13    "length_months": 0,
14    "unit_count": 30,
15    "unit_name": "minute",
16    "display_name": "30 Minutes"
17  },
18  {
19    "period_id": "10DAY",
20    "length_seconds": 864000,
21    "length_months": 0,
22    "unit_count": 10,
23    "unit_name": "day",
24    "display_name": "10 Days"
25  }
26]
```

#### **Get specific rate**

This request retrieves the exchange rate for a specific base and quotes assets at a given time or the current rate. It is useful for applications that need real-time or historical exchange rate data for specific asset pairs.

```
1{
2    "time": "2024-05-23T12:25:21.0000000Z",
3    "asset_id_base": "BTC",
4    "asset_id_quote": "USD",
5    "rate": 69856.447113757912606998861527
6}
```

Summary
-------

Exchange rates are one of the most valuable tools for market analysis and trading. In the crypto world, where data changes even more quickly and values are more volatile, accurate exchange rates are even more important. It is essential to understand the differences between the types of exchange rates and how mechanisms calculate them.

Our Market Data API brings together the best features of all exchange rates to offer accurate and reliable cryptocurrency exchange rates. It collects data from many high-quality sources to cover the whole market and reduce errors. The API filters out old or unusual data and updates the rates regularly to keep up with market changes. Using advanced calculations like Volume-Weighted Average Price (VWAP), our Market Data API provides precise and dependable exchange rates, helping traders and investors make smart decisions in the fast-changing world of cryptocurrencies.

***Find out other valuable features of our Market Data API on our [product page](https://www.coinapi.io/market-data-api) or see [the documentation](https://docs.coinapi.io/market-data/).***

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