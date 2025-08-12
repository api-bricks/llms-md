CoinAPI.io Blog - Level 1 vs Level 2 vs Level 3 market data: How to read the crypto order book

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

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F864140657bd92584430501b573b01ae0314cbc3d-800x800.png&w=96&q=75)Ada

June 12, 2025

Level 1 vs Level 2 vs Level 3 market data: How to read the crypto order book
============================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb181b5b211d803aa3077285f8f214bf8e8b0947b-1000x501.png%3Frect%3D0%2C34%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

**In crypto, your edge lives in the data. Choose the wrong level of market depth, and your strategy falls apart before it begins.**

That’s why understanding **Level 1, Level 2, and Level 3 market data** isn’t just technical trivia; it’s a core part of building smarter trading systems. These levels define how much of the order book you can actually see, from basic bid-ask prices to the full queue of every order in the market.

Here’s how each one works, and when you’ll need it.

Level 1, Level 2, and Level 3 market data explained
---------------------------------------------------

Think of the market like a busy restaurant with a waitlist system:

* **Level 1 market data** is what the host tells you when you walk in: the name of the next party to be seated (best bid and ask) and how long they’ve been waiting (last trade). It’s a high-level snapshot — helpful, but limited.
* **Level 2 data** is like seeing the entire waitlist. You know how many parties are ahead of you, how big each group is, and how long they’ve been waiting. This gives you a better sense of the flow and where the bottlenecks are, much like viewing the full depth of the order book.
* **Level 3 market data** is what the restaurant staff sees. You can track every individual party: who arrived first, who canceled, who changed their group size, and in what order they’ll be seated. That’s equivalent to seeing every individual order, timestamp, and queue position in the market.

The deeper you go, from Level 1 to Level 3, the more visibility and predictive power you gain. And in trading, that edge can make all the difference.

What is Level 1 market data?
----------------------------

**Level 1 market data** shows the most essential market information:

* The best bid and best ask (top of book)
* The last trade price
* The trade volume at the best bid and ask

This data provides a **high-level snapshot of market activity**. It’s lightweight, fast, and perfect for:

* Price tracking and charting
* Retail crypto dashboards
* Basic trading alerts
* Low-frequency or long-hold strategies

How to read Level 1 market data
-------------------------------

Reading Level 1 market data is simple: look at the **best bid** and **best ask** prices to understand where buyers and sellers are positioned. The **bid** is the highest price someone is willing to pay; the **ask** is the lowest price someone is willing to sell for. The **spread** between them shows how tight or liquid the market is. Combine this with the **last trade price** to see the most recent executed price.

Here’s an example snapshot of Level 1 market data for BTC/USDT:

```
1
2Best Bid: 28,500 USDT
3Best Ask: 28,505 USDT
4Last Trade: 28,502 USDT
5Bid Volume: 0.75 BTC
6Ask Volume: 0.60 BTC
```

In this case:

* The **spread** is 5 USDT
* The market is relatively tight (good for active traders)
* You can see recent activity around 28,502, and buyers are showing stronger volume at the bid

Level 1 gives you the immediate surface of the market, perfect for price tracking, simple strategy triggers, or mobile trading dashboards.

What is L2 market data?
-----------------------

**Level 2 market data** shows the full depth of the order book, beyond just the best bid and ask. It includes:

* Multiple price levels on both the bid and ask sides (e.g., top 10)
* Volume available at each level
* Real-time view of market liquidity and price pressure

This data is essential for traders who want to:

* Model slippage and execution risk
* Detect order book imbalances
* Build high-frequency or passive trading strategies

### Why some traders avoid it and what they’re missing

Many algo traders skip Level 2 because:

* It’s harder to access or model in real time
* The data format varies across exchanges
* They’re unsure how to extract reliable signals

But those who **do** use it often report:

* Better order timing and execution logic
* Deeper insight into short-term supply/demand
* More effective arbitrage and latency strategies

How to read level 2 market data
-------------------------------

Level 2 market data, often referred to as the order book, shows the *real-time supply and demand* at different price levels. Unlike L1 (which only shows top-of-book), L2 reveals the full depth of bids and asks.

Here’s a snapshot from our sample file (`BINANCE_SPOT_BTC_USDT-Orderbooks.csv`):

```
1makefile
2
3timestamp             | price      | size      | side
4----------------------|------------|-----------|-------
52024-12-10T14:32:01Z  | 41250.50   | 0.584     | bid
62024-12-10T14:32:01Z  | 41250.00   | 1.122     | bid
72024-12-10T14:32:01Z  | 41251.00   | 0.340     | ask
82024-12-10T14:32:01Z  | 41251.50   | 0.945     | ask
9
10
```

Each line represents resting liquidity:

* **Price**: the level at which orders are waiting
* **Size**: the cumulative quantity available at that level
* **Side**: bid (buy interest) or ask (sell interest)

🔗 Want to see how CoinAPI structures Level 2 data? Check out the [CoinAPI Market Data API documentation](https://docs.coinapi.io/market-data/rest-api/#order-book-level-2) for real-time and historical order book access.

### What to look for

* **Depth Imbalance**: if bid size >> ask size at top levels, the market may be skewed bullish
* **Liquidity Clustering**: Large volumes at a single price can indicate institutional activity
* **Microstructure Signals**: combine price movement with queue depth to model fill potential or predict breakouts

Why accessing L2 data still frustrates so many traders
------------------------------------------------------

In theory, L2 data is publicly available from most crypto exchanges. In practice? It’s a minefield. Traders on forums regularly report issues like rate limits, broken WebSocket connections, schema mismatches, or struggling to rebuild full order books from fragmented updates. As one user put it: *“You can get L2 data, but you also need to build half an exchange backend just to use it.”*

CoinAPI simplifies this by delivering:

* Pre-normalized L2 feeds from 370+ venues
* Full-depth snapshots and incremental updates
* Historical L2 flat files for backtesting
* Real-time WebSocket streams with built-in reconnection logic

This allows quants, researchers, and trading engineers to focus on the signal, not the infrastructure.

*“With CoinAPI’s L2 stream, we went from missed fills to real-time book tracking in under 3 hours.”*

Why L2 order book data is so painful to work with
-------------------------------------------------

Quantitative traders frequently ask the same question: *“Where can I get reliable, normalized L2 order book data for crypto?”* The reality is, most exchanges stream L2 updates in fragmented formats with different symbols, update intervals, and depth limits. To reconstruct the full order book, you often need a message queue, an in-memory database, custom normalization logic, and continuous monitoring for feed drops. And that’s just to get started. CoinAPI eliminates that complexity by delivering normalized, incremental L2 updates across 370+ exchanges and providing historical order book snapshots so you can backtest liquidity-sensitive strategies without rebuilding an exchange backend.

### Why “L2 API support” doesn’t always mean it’s usable

Plenty of exchanges and platforms advertise Level 2 Market data API access, but many algo traders find out the hard way that *having* access doesn’t mean you can *use* it efficiently. As one user put it: *“I had to build a whole WebSocket reconnection loop just to keep the feed alive.”* The problems include inconsistent depth levels, missing snapshots, update throttling, and no standard format across venues.

That’s why serious quant teams and trading engineers turn to providers like CoinAPI, where Level 2 market data is:

* Normalized across exchanges
* Available via flat file or low-latency WebSocket
* Designed for real-time or backtest-ready use
* Backed by consistent, well-documented schemas

With this setup, you can skip the plumbing and go straight to modeling.

Curious why data normalization matters so much when working with Level 2 feeds?

👉 Check out our blog post: [**Why is it critical to normalize cryptocurrency trade data?**](https://www.coinapi.io/blog/why-is-it-critical-to-normalize-cryptocurrency-trade-data)

### When charting platforms don’t go deep enough

Platforms like TradingView offer great visualizations but when it comes to **real-time Level 2 data**, most users hit a wall. Either the data is locked behind costly professional plans, or it’s limited to surface-level bid/ask quotes without full order book depth. As one trader put it: *“I just want to see where the volume is stacking, but I can’t get that without paying hundreds.”* At CoinAPI, we believe **transparency and access shouldn't be luxuries**. That’s why our L2 data streams offer full market depth across hundreds of exchanges in real time and without artificial paywalls. So you don’t just see the price. You see what’s about to move it.

Does level 2 market data matter?
--------------------------------

We hear it a lot: *“Is Level 2 data really worth it, or is it just noise?”*

If you're holding BTC for six months or riding a macro trend in SOL, the answer might be no; L2 probably won’t move your decision-making. But for scalpers, arbitrageurs, and anyone executing in fast or thin markets, **Level 2 is pure signal**.

It reveals what price charts can't:

* Hidden liquidity just below the surface
* Large orders are stacking under the spread
* Imbalances that suggest pressure before a breakout

As one trader put it: *“Level 2 doesn’t tell you where price is, it tells you where it’s likely to go next.”*

With CoinAPI, you get normalized Level 2 market data across 370+ exchanges, clean, consistent, and ready when depth starts to matter.

What is level 3 market data?
----------------------------

**Level 3 market data** shows the most detailed view of market activity, including every individual order in the book. Unlike Level 1 and Level 2, which aggregate orders by price level, Level 3 reveals:

* Each individual limit order with size, price, and timestamp
* Order IDs and sequence numbers
* Cancellations, modifications, and exact queue position

This data is used for:

* Market microstructure analysis
* Queue modeling and latency optimization
* Order flow prediction
* High-frequency trading systems

Level 3 market data provides the raw, unfiltered truth of market intent, but it requires significant infrastructure and parsing power to use effectively.

How to read level 3 market data
-------------------------------

Reading Level 3 market data means analyzing **individual orders** in the book, not just price levels or size aggregates. Each entry includes a unique **order ID**, its **exact price**, **quantity**, and **timestamp**, along with metadata like **sequence number** and **event type** (placement, modification, or cancellation).

Here’s a simplified example:

```
1makefile
2
3timestamp             | order_id        | price     | size    | side | event
4----------------------|------------------|-----------|---------|------|--------
52024-12-10T14:32:01Z  | 8432089231       | 41250.50  | 0.40    | bid  | new
62024-12-10T14:32:02Z  | 8432089231       | 41250.50  | 0.25    | bid  | modify
72024-12-10T14:32:03Z  | 8432089231       | 41250.50  | 0.00    | bid  | cancel
8
9
```

With this view, you can:

* Reconstruct exact queue positions
* Track how liquidity enters and exits the book
* Detect order layering, iceberg strategies, or spoofing
* Build models that go beyond price to **intent**

It’s raw and high-volume, but if you’re working in HFT or researching market microstructure, it’s the closest you’ll get to “seeing the game board.”

Want to access Level 3 data with CoinAPI?

[Check the CoinAPI Order Book L3 API documentation](https://docs.coinapi.io/market-data/rest-api/order-book-l3) for both real-time and historical retrieval options.

The role of level 3 market data in crypto trading
-------------------------------------------------

While Level 2 (L2) data provides aggregated order book information, Level 3 (L3) data offers a more granular view, detailing individual orders, including their size, price, and timestamps. This level of detail can be invaluable for certain trading strategies, such as high-frequency trading (HFT) and advanced market microstructure analysis.

However, accessing L3 data in the cryptocurrency space presents challenges:

* **Limited Availability**: Not all exchanges provide L3 data. For instance, while Coinbase and Bitfinex offer such detailed information, major platforms like Binance have historically limited access to only L2 data. This inconsistency can hinder comprehensive market analysis across multiple venues.
* **Transparency Concerns**: Some traders express skepticism about the transparency of crypto operations. The lack of widespread L3 data availability raises questions about the openness of certain exchanges and their willingness to share detailed market information.
* **Tooling and Infrastructure**: Analyzing L3 data requires specialized tools. Platforms like VisualHFT have developed solutions to handle L3 data from exchanges that provide it. However, their open-source versions might support only L2 data, necessitating investment in commercial tools for full L3 analysis.

Given these factors, traders must weigh the benefits of L3 data against the challenges of obtaining and processing it. For many, L2 data, which offers a balance between detail and accessibility, remains the primary resource for developing and executing trading strategies.

Leveraging level 3 market data in advanced trading strategies
-------------------------------------------------------------

While Level 2 (L2) data provides aggregated order book information, Level 3 market data offers a granular view of individual orders, including their size, price, and timestamps. This detailed perspective is crucial for certain trading approaches:

* **High-Frequency Trading (HFT)**: Firms engaged in HFT rely on L3 data to analyze order flow and predict short-term market movements. The ability to see individual order placements and cancellations allows for more precise algorithmic strategies.
* **Order Book Dynamics**: Understanding the behavior of market participants at the micro-level enables traders to identify patterns, such as spoofing or layering, and adjust their strategies accordingly.

However, accessing and utilizing L3 data comes with challenges:

* **Data Volume and Processing**: The sheer volume of L3 data requires a robust infrastructure to process and analyze in real-time. Traders must ensure their systems can handle this influx without latency issues.
* **Limited Access for Retail Traders**: Historically, L3 data has been accessible primarily to institutional traders. However, some platforms have started to offer this data to retail traders, expanding opportunities for more sophisticated trading strategies.

Incorporating L3 data into trading strategies can provide a competitive edge, but it's essential to weigh the benefits against the technical and logistical requirements.

Summary: L1 vs L2 vs L3 crypto market data
------------------------------------------

![Summary: L1 vs L2 vs L3 Market Data](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F7cabd1931e6816266204899e7792ed151bc42f41-1270x758.png&w=1920&q=75)

When should you use each?
-------------------------

![When should you use each?](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F686ff12fa84277bf537b3b987fcc8b46242904d5-1066x594.png&w=1920&q=75)

### TL;DR

The difference between Level 1, Level 2, and Level 3 market data isn’t just technical; it’s strategic. The deeper your visibility, the sharper your decisions.

Whether building an arbitrage engine, modeling execution risk, or analyzing market microstructure, **CoinAPI delivers the data edge** you need. With one of the best crypto exchange APIs available, we give you normalized, real-time access to Level 2 and Level 3 data from over 370 venues.

Ready to build with real depth?

👉 [Start with CoinAPI](https://www.coinapi.io/contact)

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