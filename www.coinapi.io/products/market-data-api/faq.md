Market Data API FAQ | Help & Troubleshooting | CoinAPI - Market Data API FAQ

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

![background](https://cdn.sanity.io/images/o65xz72l/production/5dcb38164a73643922ee84916f563a1fd88c846e-1632x313.svg)![background](https://cdn.sanity.io/images/o65xz72l/production/c3ec9102a1676a96a53eca8d738ef96129562e60-1632x313.svg)

* Use Cases
* [Pricing](/products/market-data-api/pricing)
* [FAQ](/products/market-data-api/faq)
* [Developers](https://docs.coinapi.io/market-data)
* Tutorials

Table of Contents

* [General](#section-5007b78310a2)
* [API Usage, credits and limits](#section-e2f1768cd16a)
* [Billing, payment & subscriptions](#section-06629f9cacfa)
* [Security and Privacy](#section-71e0b680a33a)
* [API access & integration](#section-b8c8e8e3b943)
* [Market data API](#section-f43edc0faf11)

General

What is CoinAPI?

Is there an API endpoint to check my usage, or is it only visible on the dashboard?

Can I get a custom plan based on my data needs?

Are subscription payments executed automatically?

Are you planning to add an order exchange fee feature?

Can I get exchange wallet deposit and withdrawal status?

Can I get the XML or CSV instead of the JSON output format?

Can I have multiple API keys in one account?

Can I have multiple subscriptions?

Can I participate in the CoinAPI GitHub repository?

Can I use the API commercially to show prices on my website?

Can I use the API to show graphs, charts or tables?

Do you provide historical market data in flat files?

Do you offer discount for University/non-profit/research-only usage?

Do you have a Status Page?

Does CoinAPI provide asset icons/images of the cryptocurrencies?

How can I set custom timezone in the data?

Does CoinAPI offer SLAs (Service Level Agreements) for enterprise clients?

How long does it take to integrate CoinAPI?

How can I be notified about CoinAPI issues or incidents?

Is there an SLA agreement available with CoinAPI?

Should we file a support ticket every time we experience a problem?

What types of data does CoinAPI provide?

Do you offer integration assistance or paid onboarding support?

API Usage, credits and limits

Where can I get more information about API Usage and Limits?

How does CoinAPI’s credit system work? Do I need to preload credits, and how fast are charges reflected?

How do I enable overage?

What happens if I exceed my daily REST API request limit on my CoinAPI plan?

Why do some CoinAPI responses not include rate limit headers?

How can I check my historical API usage with CoinAPI?

How can I retrieve more than 100 items in a single API response?

I barely use the REST API. Why is my usage still so high?

How do I calculate the number of requests I’ll be making for a specific query?

Why does using limit=1 still count as 1 full request in my API usage? Isn't pricing based on 100 data points?

Billing, payment & subscriptions

Can I cancel my subscription anytime?

Can I still use my API key if I cancel my subscription?

How to reactivate my canceled subscription?

How to subscribe to the API?

How to upgrade/downgrade my subscription?

What do I need to complete a subscription payment?

Do you accept bank or wire transfers?

How should I handle payment errors during sign-up?

Is there a free tier for CoinAPI's Market Data API?

Can I top up credits at a discounted rate on different days under the metered plan?

What happens if we exceed our credit limit? Will we be notified the same day? And how do upgrades work on an annual subscription?

Can I customize my plan?

How do I pay overdue invoices?

What is a billing cycle?

Security and Privacy

What CDN does the API use?

What security mechanisms does CoinAPI use to protect my data?

What should I do if my API key was compromised?

API access & integration

How can I troubleshoot FIX API logon issues with CoinAPI?

Where are CoinAPI’s servers located, and how does latency vary by region?

How does CoinAPI calculate cryptocurrency exchange rates?

How can I fix certificate validation errors when connecting to CoinAPI?

How can I use CoinAPI from MATLAB?

What programming languages are supported by CoinAPI?

What timezone does CoinAPI use for date and time values?

Where can I find API examples and SDK source code for CoinAPI?

Can using a VPN affect my connection to CoinAPI?

How should I document and troubleshoot CoinAPI connectivity issues?

Why am I getting an "Invalid API Key" error after generating a new key?

How do I troubleshoot API errors?

How do I generate an API key for FIX API access?

Why does my WebSocket connection keep disconnecting with code 1006 and no reason?

Market data API

Do crypto exchanges send duplicate trade data messages?

Can historical order books reconstructed from L2 updates be crossed (bid-ask overlap) occasionally?

Do you collect order books as snapshots or in streaming mode?

Do you offer historical crypto futures market data?

Do you provide historical options data?

Do you provide market data in a normalized format?

Do you provide time-based Order Book aggregated data (e.g., OHLCV or interval-based snapshots)?

How are order book data snapshots provided?

How does the full orderbook stream work?

How historical raw market data is being sourced?

How much historical data does CoinAPI have?

How much historical data can I fetch from a single query?

What data types do you support?

What does high frequency historical data mean?

What is the difference between futures and perpetual swaps contracts?

What can L2 order book data be used for?

What can L3 order book data be used for?

What metrics does CoinAPI use to evaluate cryptocurrency exchange performance and activity?

Why does the data source matter, and why does CoinAPI use real-time WebSocket feeds instead of relying on REST endpoints?

Why is the volume\_1day\_usd value for BTC or ETH higher than on platforms like CoinGecko?

Why am I receiving multiple OHLCV updates for the same time window via WebSocket?

Can I retrieve time-aggregated order book data using period\_id from the REST API?

Why is the /v1/orderbooks/{symbol\_id}/history endpoint slow for symbols like BINANCE\_SPOT\_BTC\_USDT?

Does CoinAPI provide data for blockchain verification, deposit/withdrawal status, or token contract addresses?

Does CoinAPI provide aggregated Kline, order book, trades, or market sentiment data across multiple exchanges?

Do you provide OHLC, turnover, trades, market cap for perpetuals, or funding rate data?

Why am I only seeing SPOT symbols at /v1/symbols? How can I get PERP data?

How much data would I use tracking real-time prices for 100 coins, updated 24 times per day?

Why does the /v1/symbols endpoint time out when I try to load all symbol metadata?

Do I need to send an unsubscribe message before closing a WebSocket connection?

Can I get historical ask, bid, and order book depth data from Binance, including snapshots and real-time updates from the past year?

How can I access historical bid/ask data and order book snapshots from Binance? Which CoinAPI product or plan should I choose?

Can I retrieve aggregated liquidity data for mid-price ±X% over time intervals (e.g., 1h, 8h, 1d)?

What is the unit of volume\_1day in the /v1/symbols endpoint?

Why am I receiving an empty response when fetching today’s historical order book data?

Why are the X-RateLimit-Remaining and X-RateLimit-Reset headers missing from the OHLCV Historical API responses?

How can I handle large result sets with the Historical OHLCV endpoint when the response doesn’t indicate total rows?

Can I connect to the main WebSocket DS endpoint from multiple environments?

How many credits are used by the OHLCV Exchanges endpoint?

Can I confirm that LMAX Digital data is available?

Is the datacenter located in London?

Is there any delay that occurs on your end?

How is L2 Order Book data aggregated across exchanges, particularly when combining centralized and decentralized sources?

How are price levels with different tick sizes reconciled?

Are synthetic DEX order books (e.g., Uniswap pools) combined with CEX data in the same aggregate feed?

If synthetic DEX and CEX order books were combined, how is the depth normalized or bucketed to make them comparable?

Is there a reference list of the available aggregated symbol IDs (e.g., BTC\_USD, ETH\_USD)?

How can I estimate liquidity and slippage across exchanges — especially when quote currencies differ (e.g., BTC/USDC vs BTC/USDT)?

Which exchanges support L3 (Full Depth Order Book) data?

I can’t find the perpetual (PERP) symbols for my exchange. Where are they?

Can I use your data to analyze true market trades involving limit orders?

How do I read the Usage Metrics Dashboard and understand the difference between Tier 1 and Tier 2 data?

How do I filter symbols in my subscription?

Can I test the LMAX add-on for a few days?

How do I connect to the FIX API — via gateway or data feed?

Does the Startup plan include buy/sell volume and percentage data?

How do I calculate REST credit usage for the /v1/orderbooks/:symbol\_id/history endpoint?

Why are some trades received via WebSocket showing zero volume? Should they affect OHLC calculations?

Why am I seeing trades with zero size in non-index symbols like BITRUE\_SPOT\_XAUT\_USDT?

If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?

Do you support real-time streaming via WebSocket for trades, quotes and L2 Order Book / Depth?

Do you offer data for BTC/USDT and ETH/USDT pairs, and support futures market data?

What are the current rate limits and latency expectations for WebSocket streaming and REST polling endpoints?

Why do some order books have crossed prices (bid ≥ ask)?

Why is CoinAPI’s OHLCV data different from the exchange chart?

How can I view a list of symbols by exchange, market type, or asset in CoinAPI?

What does a WebSocket reconnect message mean, and how should I handle it?

What are the risks of using multiple concurrent WebSocket connections with the same API key?

Why do some CoinAPI symbol IDs have an extra prefix or suffix?

How granular is CoinAPI’s data?

How is trade volume calculated in CoinAPI?

How can I avoid losing messages or experiencing delays when using CoinAPI’s WebSocket stream?

Is latency higher for exchanges that provide only REST APIs?

How can I query OHLCV data filtered by specific coins and exchanges using the REST API?

Why does the REST API return an empty array for OHLCV data instead of a 550 error?

What are the benefits of using the CoinAPI WebSocket SDK?

What data is delivered using CoinAPI’s local sites?

What should I do if I encounter missing price data or data gaps?

What is the typical latency of CoinAPI's REST Market Data API?

### Crypto API made simple: Try now or speak to our sales team

[Start for free](https://www.coinapi.io/products/market-data-api/pricing)[Get in touch](https://www.coinapi.io/contact-us)

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