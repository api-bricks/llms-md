CoinAPI.io Blog - 13 Advanced Order Types That Can Increase Your Profits in Crypto

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

September 09, 2024

13 Advanced Order Types That Can Increase Your Profits in Crypto
================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F7b7d431556639efac5b0ecd09ad19db4270e885d-1001x500.png%3Frect%3D0%2C33%2C1001%2C435%26w%3D920%26h%3D400&w=1920&q=75)

Market and limit orders are the most common order types known in crypto. However, for professional traders, institutional investors, and hedge funds they are not enough. Professionals require better risk management, higher flexibility, and automation. The advanced order types are precisely the answer to these needs. You can place them through such tools as [EMS Trading API](https://www.coinapi.io/ems-api) - a unified trading platform integrated with multiple cryptocurrency exchanges. So, what are advanced order types and their use cases?

Market orders vs limit orders vs stop orders - a brief reminder
---------------------------------------------------------------

*If you know what market orders and limit orders are, skip to the next paragraph.*

Market orders are executed immediately at the best available price in the market. You can use them when immediate execution is more important than price control, such as during fast-moving markets or when there's a need to enter or exit a position quickly. While market orders guarantee execution, they don't guarantee a specific price.

At the opposite pole lies the limit order. It's an instruction to buy or sell a security at a specific price or better. For example, if a currency's price is hovering around $150 and you're unwilling to pay more than $135 for it, you can set that as your limit. However, with limit orders, there's no certainty about if or when the transaction will take place.

Another type, stop orders, becomes a market order when the market price reaches a specified stop price. This helps automate selling to minimize losses or lock in profits after a large price movement.

![Market order, limit order, and stop order shown on a graph](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fae1da14de654f9a1dd95c9a32aa3a879fde6e63d-800x400.png&w=1920&q=75)

Advanced order types - overview and use cases
---------------------------------------------

### 1 . Stop-Limit Order

A stop-limit order is a combination of a stop order and a limit order. When the market price reaches the stop price, it triggers a limit order at the specified limit price instead of a market order. This gives traders more control over their execution price compared to a standard stop order.

> 💡**Use case**: Imagine you bought Bitcoin at $30,000 and want to protect your downside while ensuring you don't sell at an unfavorable price due to a sudden market fluctuation. You might set a stop-limit order with a stop price of $28,000 and a limit price of $27,800. If Bitcoin's price falls to $28,000, it triggers a limit order to sell at $27,800 or better. This strategy helps protect against significant losses while also guarding against executing at an unexpectedly low price due to temporary market volatility. This reduces the risk of slippage, but it may result in no execution if the price doesn’t reach the limit.

### 2. Take-Profit Orders

Take-profit orders are designed to automatically close a position when it reaches a predetermined profit target. Once the specified price level is reached, the order is executed as a market order, securing the profit for the trader.

> 💡**Use case**: Let's say you've bought Ethereum at $2,000 and you believe it has the potential to rise, but you want to lock in profits if it reaches $2,500. You could set a take-profit order at $2,500. If Ethereum's price reaches this level, your position will automatically be closed, securing your profit regardless of whether you're actively monitoring the market.

### 3. Iceberg Orders

Iceberg orders are large orders that are divided into smaller, visible portions. Only a small part of the total order quantity is shown in the order book at any given time. As the visible portion gets filled, a new portion becomes visible, much like the tip of an iceberg emerging as the visible part melts away.

> 💡**Use case**: Suppose a large institutional investor wants to buy 1,000 Bitcoin but doesn't want to reveal the full size of their order to avoid influencing the market. They might use an iceberg order, showing only 50 Bitcoin at a time in the order book. This strategy helps them acquire their desired position without causing a significant price impact, which could occur if their full intention was known to the market.

### 4. Good Till Cancel (GTC)

A Good Till Cancel order remains active in the market until it is either fully executed or explicitly canceled by the trader. Unlike day orders that expire at the end of the trading session, GTC orders can persist for an extended period, sometimes indefinitely, depending on the exchange's policies.

> 💡**Use case**: You might use a GTC order if you want to buy a specific cryptocurrency at a certain price, but you're not in a hurry and are willing to wait for the market to reach your desired entry point. For instance, if you want to buy Cardano (ADA) at $0.50, but it's currently trading at $0.60, you could place a GTC limit buy order at $0.50. This order would remain active until either it's filled when ADA reaches $0.50, or until you decide to cancel it.

### 5. Good Till Time (GTT)

A Good Till Time order is similar to a GTC order but with a specific expiration date and time. The order remains active in the market until it is either executed, canceled by the trader, or the specified expiration time is reached.

> 💡**Use case**: Suppose you believe a particular altcoin will experience increased volatility due to an upcoming network upgrade scheduled in two weeks. You want to set a buy order at a favorable price, but you don't want the order to remain active indefinitely. You could use a GTT order, setting it to expire just after the upgrade date. This way, if your target price isn't reached within your expected timeframe, the order will automatically expire, freeing up your funds for other opportunities.

### 6. Fill or Kill (FOK)

A Fill or Kill order must be executed immediately and in its entirety, or it will be canceled completely. There is no partial filling with FOK orders - it's all or nothing. This order type is typically executed within seconds of being placed.

> 💡**Use case**: FOK orders are particularly useful when dealing with less liquid cryptocurrencies or when timing is crucial. For example, if you want to buy exactly 100 units of a low-liquidity token and you're not willing to accept any partial fills, you might use an FOK order. This ensures that you either get your entire desired quantity at your specified price, or the order is canceled, preventing you from ending up with an incomplete position.

### 7. Immediate or Cancel (IOC)

An Immediate or Cancel order is similar to FOK, but it allows for partial fills. The order attempts to execute immediately, filling as much as possible at the specified price or better. Any portion of the order that cannot be filled immediately is canceled.

> 💡**Use case**: IOC orders are valuable when you want to take advantage of current market conditions but aren't necessarily committed to filling your entire order. For instance, if you want to buy up to 10 Ethereum at the current market price, but you're okay with getting less if 10 aren't available, you might use an IOC order. This would fill as much of your order as possible at the current price and cancel any unfilled portion, preventing your order from lingering in the order book.

### 8. Maker or Cancel (MOC)

A Maker or Cancel order is designed to ensure that the order is only executed if it can be added to the order book as a maker order, thus adding liquidity to the market. If the order would immediately match with an existing order (making it a taker order), it is canceled instead.

> 💡**Use case**: MOC orders are particularly useful for traders who want to avoid paying taker fees and prefer to act as liquidity providers. For example, if you're running a market-making strategy on a cryptocurrency exchange, you might use MOC orders to ensure that all your orders are adding liquidity to the market. This can be beneficial both in terms of lower fees and in some cases, earning rebates for providing liquidity.

### 9. Auction-only

Auction-only orders are specifically designed to participate in auction periods, which some cryptocurrency exchanges conduct at market open, close, or during other specified times. These orders are only executed during these auction periods and do not interact with the regular order book.

> 💡**Use case**: This advanced order type can be useful for traders who want to participate in price discovery processes or take advantage of potentially higher liquidity during auction periods. For instance, if you believe that the opening auction for Bitcoin futures contracts on a particular exchange often sets the tone for the day's trading, you might use an auction-only order to ensure you participate in this price formation process.

### 10. Post-Only Order

A Post-Only order ensures that the order is added to the order book as a maker order, providing liquidity rather than taking it. If the order immediately matches with an existing order in the book (making it a taker order), it is either canceled or re-priced to ensure it remains a maker order, depending on the exchange's specific implementation.

Post-Only Orders and Maker or Cancel (MOC) orders are similar and often confused but there are some subtle but important differences between them. The main one lies in how these orders behave when they would potentially match immediately with an existing order in the book.

* A Post-Only order might be repriced by some exchanges to ensure it remains a maker order. For example, if you place a Post-Only buy order at $100 and the current best ask is $99.99, the exchange might reprice your order to $99.98 to keep it as a maker order.
* A MOC order, on the other hand, will always be canceled if it matches immediately. There's no repricing involved.

> 💡**Use case**: Post-Only orders are particularly useful for [high-frequency trading strategies](https://www.coinapi.io/blog/high-frequency-treading-strategies-in-crypto) or for traders who want to ensure they always receive maker fees (which are often lower than taker fees). For instance, if you're running an [arbitrage bot](https://www.coinapi.io/use-case/coinapi-for-algo-trading-crypto-bot) that profits from small price discrepancies between exchanges, you might use Post-Only orders to ensure you're always adding liquidity and minimizing your fee exposure.

### 11. Trailing Stop Order

A Trailing Stop order sets the stop price at a fixed amount or percentage away from the current market price. As the market price moves in a favorable direction, the stop price adjusts accordingly, maintaining the specified distance. If the market reverses, the stop price remains fixed at its most recent favorable level.

> 💡**Use case**: Trailing Stop orders are excellent for protecting profits in a trending market while allowing for maximum potential gain. For example, if you bought Ethereum at $2,000 and set a trailing stop of 10%, your initial stop would be at $1,800. If Ethereum's price rises to $3,000, your stop would adjust to $2,700. This way, you're protected from a significant reversal while still allowing your profits to run if the uptrend continues.

### 12. Bracket Orders

A bracket order is a combination of multiple orders designed to automate exit strategies. It includes an initial order along with two protective orders: a take-profit order and a stop-loss order. Once the initial order is filled, the two protective orders are activated. If either of these orders is triggered, the other is automatically canceled.

> 💡**Use case**: Bracket orders are particularly useful for traders and institutions who want to automate their risk management and profit-taking strategies. For instance, you might place a bracket order to buy Bitcoin at $30,000, with a take-profit order at $33,000 and a stop-loss at $28,500. Once your buy order is filled, both the take-profit and stop-loss orders are activated, ensuring that your position is automatically managed according to your predetermined strategy, regardless of market movements.

### 13. One-Cancels-the-Other (OCO) Order

An OCO order combines two orders with the stipulation that if one order is executed, the other is automatically canceled. Typically, this involves a limit order to take profit and a stop order to limit losses, but it can be used with various order types.

> 💡**Use case**: OCO orders are valuable when you want to set both a profit target and a stop-loss level for an existing position. For example, if you're holding Litecoin that you bought at $100, you might set an OCO order with a limit sell order at $120 (to take profits) and a stop-loss order at $90 (to limit potential losses). Whichever price is reached first will trigger that respective order and cancel the other, ensuring that your position is closed according to your strategy without requiring constant monitoring.

Advanced order types - why use them?
------------------------------------

After reading the above use cases, you already know what are the benefits of using advanced order type. However, let’s sum it up.

### Risk management

Advanced order types like stop-loss and take-profit orders help traders manage their risk by automatically executing trades at predefined price levels.

### Execution precision

Orders such as iceberg orders allow large trades to be executed in smaller, more manageable chunks, reducing market impact and avoiding revealing the full size of the order.

### Flexibility

Advanced order types provide more options for traders to execute their strategies, such as setting specific time frames for orders (GTC, GTT) or ensuring immediate execution (FOK, IOC).

### Liquidity provision

Orders like Maker or Cancel (MOC) ensure that the trader adds liquidity to the market, which can be beneficial in markets where liquidity is a concern.

### Automated trading

Advanced order types facilitate automated trading strategies, allowing traders to set conditions under which trades are executed without constant monitoring.

Best practices for using advanced order types
---------------------------------------------

Despite advanced order types giving you a lot of room for automation, they are not self-players that you just set up once and wait for the revenue to come in. Several conditions are required to be able to use them successfully:

### Understand the market

Before using advanced order types, traders should have a good understanding of the market conditions and how different order types can impact their trades.

### Set clear objectives

Traders should have clear objectives for each trade and choose the order type that best aligns with their strategy.

### Monitor orders

Even with advanced order types, it's important to monitor orders to ensure they are executed as expected and to make adjustments as needed.

### Use in conjunction with other tools

Advanced order types can be more effective when used in conjunction with other trading tools and strategies, such as technical analysis and risk management techniques.

This may also be of interest to you:

[3 core statistical arbitrage strategies in crypto](https://www.coinapi.io/blog/3-statistical-arbitrage-strategies-in-crypto).

Have any questions about advanced order types and capabilities of [EMS Trading API](https://www.coinapi.io/ems-api)? You’re more than welcome to [contact us](https://www.coinapi.io/contact-us).

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