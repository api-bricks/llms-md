CoinAPI.io Glossary - OHLCV

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

### OHLCV

OHLCV stands for Open, High, Low, Close, and Volume - these are the key data points used to track price movement of stocks, cryptocurrencies, or other financial instruments over a specific time period (like hourly or daily).

Table of Contents

* [What is OHLCV?](#link-e8df54e3e075)
* [How OHLCV Data Works](#link-363fa6f44ef7)
* [OHLCV in Cryptocurrency Trading](#link-3de2238ca7ff)
* [Did You Know?](#link-f67db67d6f4e)
* [How CoinAPI Delivers OHLCV Data](#link-2af9a9bfe80d)
* [Technical Analysis with OHLCV](#link-fd8ec809eb31)
* [Things to Remember About OHLCV](#link-5f867b6cb0bc)

**Every cryptocurrency trade tells a story. But when Bitcoin moves from $40,000 to $67,000 and back to $50,000 in a single day with 50,000 transactions, how do you capture that chaos in a format that algorithms can understand?** Enter OHLCV - the five-number summary that transforms millions of individual trades into the building blocks of every trading strategy, technical indicator, and market analysis tool ever created.

While traders see candlestick charts, algorithms see OHLCV data streams - the mathematical DNA of every price movement in cryptocurrency history.

What is OHLCV?
--------------

OHLCV is a standardized data format that summarizes cryptocurrency price action and trading activity over specific time periods using five key metrics: Open, High, Low, Close, and Volume. This format converts complex trading activity into structured data points essential for technical analysis, algorithmic trading, and market research.

**OHLCV represents the universal language of financial markets.** Every candlestick chart, trading indicator, and market analysis tool relies on these five fundamental data points. The format provides a standardized way to compress thousands of individual cryptocurrency trades into meaningful insights about price trends, volatility, and market sentiment.

This data structure proves essential for cryptocurrency trading applications, from simple price tracking to sophisticated algorithmic strategies that process millions of OHLCV data points across multiple exchanges and timeframes.

How OHLCV Data Works
--------------------

OHLCV data aggregates all trading activity within defined time periods into five essential metrics. **Each OHLCV data point represents a complete summary** of market activity for its specific timeframe.

**The Five Components Explained:**

**Open (O)**: The first transaction price when the time period begins. For daily data, this represents the cryptocurrency price at midnight UTC.

**High (H)**: The highest price reached during the entire time period. This shows maximum buying pressure and resistance levels.

**Low (L)**: The lowest price reached during the time period. This indicates maximum selling pressure and support levels.

**Close (C)**: The final transaction price when the time period ends. This becomes the opening price for the next period.

**Volume (V)**: Total quantity of cryptocurrency traded during the period. This measures market activity and liquidity.

**Time Period Flexibility:**

* **1-minute OHLCV**: High-frequency trading and scalping strategies
* **1-hour OHLCV**: Intraday analysis and short-term trend identification
* **Daily OHLCV**: Swing trading and medium-term market analysis
* **Weekly/Monthly OHLCV**: Long-term investment and macro trend analysis

OHLCV in Cryptocurrency Trading
-------------------------------

Cryptocurrency markets generate OHLCV data continuously across hundreds of exchanges and thousands of trading pairs. **This creates the largest financial dataset in human history** - billions of OHLCV data points representing every Bitcoin, Ethereum, and altcoin transaction.

**Critical Trading Applications:**

**Technical Analysis**: OHLCV data powers every technical indicator from moving averages to RSI, MACD, and Bollinger Bands for cryptocurrency market analysis.

**Algorithmic Trading**: Trading bots process OHLCV streams to identify patterns, execute strategies, and manage risk across multiple cryptocurrency exchanges.

**Backtesting**: Historical OHLCV data enables strategy testing across years of market conditions, bear markets, bull runs, and volatility cycles.

**Market Research**: Analysts use OHLCV data to study cryptocurrency adoption, market manipulation, and institutional trading patterns.

**Real-World Example:**

Bitcoin Daily OHLCV - March 12, 2020 (Black Thursday)  
Open: $7,900  
High: $8,100  
Low: $3,850  
Close: $5,000  
Volume: 180,000 BTC

This single OHLCV data point captures one of cryptocurrency history's most dramatic price crashes, showing 50% intraday volatility and record trading volume.

Did You Know?
-------------

* The largest Bitcoin OHLCV data point recorded a 24-hour volume of 2.1 million BTC during the May 2021 market peak
* A single day of cryptocurrency OHLCV data across all exchanges represents over $100 billion in trading volume
* The most volatile OHLCV data point in crypto history showed a 95% intraday range during the 2017 altcoin bubble
* Professional trading firms process over 50 million OHLCV data points daily across global cryptocurrency markets
* The smallest timeframe OHLCV data available goes down to 1-second intervals for ultra-high-frequency trading
* During Bitcoin's 2021 bull run, daily OHLCV data showed 47 consecutive days with closing prices higher than opening prices
* Some cryptocurrency exchanges generate new OHLCV data points every millisecond during peak trading periods
* The largest OHLCV dataset spans over 4,000 cryptocurrencies across 15 years of trading history
* Machine learning models can predict short-term price movements with 68% accuracy using only OHLCV data patterns

How CoinAPI Delivers OHLCV Data
-------------------------------

CoinAPI provides comprehensive OHLCV data across 370+ cryptocurrency exchanges with standardized formatting and multiple delivery methods. The platform aggregates millions of individual trades into clean, consistent OHLCV data streams for trading applications and market analysis.

**Comprehensive Coverage**: OHLCV data for Bitcoin, Ethereum, and thousands of altcoins across major exchanges including Binance, Coinbase, Kraken, and hundreds of regional platforms.

**Multiple Timeframes**: Access 1-minute, 5-minute, 1-hour, daily, weekly, and monthly OHLCV data through unified APIs with consistent formatting across all exchanges.

**Real-Time and Historical**: Live OHLCV updates via WebSocket connections plus complete historical data back to 2010 for backtesting and research applications.

**High-Quality Data**: Advanced filtering removes wash trading, removes invalid data points, and ensures OHLCV accuracy for professional trading applications.

**Example OHLCV Request:**

GET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/history?period\_id=1HRS&limit=100

**WebSocket OHLCV Subscription:**

{  
 "type": "hello",  
 "subscribe\_data\_type": ["ohlcv"],  
 "subscribe\_filter\_symbol\_id": ["BINANCE\_SPOT\_BTC\_USDT"],  
 "subscribe\_filter\_period\_id": ["1HRS"]  
}

**Flat Files Access**: Bulk OHLCV downloads for machine learning model training, extensive backtesting, and academic research requiring years of historical cryptocurrency data.

Technical Analysis with OHLCV
-----------------------------

OHLCV data forms the foundation for every technical analysis method used in cryptocurrency trading. **Professional traders combine multiple OHLCV timeframes** to identify trends, support/resistance levels, and optimal entry/exit points.

**Popular OHLCV Applications:**

**Candlestick Patterns**: Japanese candlestick analysis using OHLCV data to identify reversal signals like doji, hammer, and engulfing patterns.

**Moving Averages**: Simple and exponential moving averages calculated from OHLCV close prices to identify trend direction and momentum.

**Volatility Analysis**: High-Low ranges and average true range calculations using OHLCV data to measure market volatility and set position sizes.

**Volume Analysis**: OHLCV volume data combined with price action to confirm trends, identify accumulation/distribution phases, and spot potential breakouts.

Things to Remember About OHLCV
------------------------------

**Universal standard**: OHLCV provides the foundational data format for all cryptocurrency technical analysis, trading algorithms, and market research applications.

**Timeframe flexibility**: Different OHLCV periods serve different trading strategies, from scalping to long-term investment approaches.

**Data quality matters**: Clean, accurate OHLCV data determines the reliability of trading strategies, backtesting results, and market analysis conclusions.

**CoinAPI advantage**: Comprehensive OHLCV coverage across 370+ exchanges with standardized formatting, real-time updates, and extensive historical data for professional applications.

**Learn more:**

To explore further:

* [CoinAPI OHLCV Documentation](https://docs.coinapi.io/market-data/rest-api/ohlcv/)
* [Understanding OHLCV in Crypto Market Data Analysis](https://www.coinapi.io/blog/understanding-ohlcv-in-market-data-analysis)

These resources provide implementation details, analysis techniques, and practical examples for developers, traders, and cryptocurrency market researchers.

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