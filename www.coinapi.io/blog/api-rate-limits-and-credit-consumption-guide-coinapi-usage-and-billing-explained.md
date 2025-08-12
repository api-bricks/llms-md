CoinAPI.io Blog - API Rate Limits and Credit Consumption Guide. CoinAPI Usage and Billing Explained

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

May 26, 2025

API Rate Limits and Credit Consumption Guide. CoinAPI Usage and Billing Explained
=================================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F7411e5f4019413b7dfed2213db65d6a75644c6f6-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

Ever been stopped cold by the message: *“You’ve hit your API rate limit”*? Whether you're running real-time dashboards, backtests, or execution systems, hitting an API rate limit disrupts everything. This guide explains exactly how API rate limits work, how CoinAPI defines and enforces quotas, and how to monitor your usage to avoid 429 errors. Learn how to optimize your requests across REST and WebSocket endpoints while scaling confidently with real-time tracking tools and overage options.

API rate limits and quotas: CoinAPI guide
-----------------------------------------

API Rate limits define how many requests you're allowed to make.

Throttling occurs when you exceed that limit. Either requests are slowed down or blocked (often with a 429 error).

These limits exist to enforce policy, protect platform stability, and ensure fairness across all users, from solo developers to institutional quant teams. They’re how we keep the system fast, reliable, and scalable.

In addition to daily quota limits, CoinAPI enforces several other restrictions to ensure fair usage and maintain optimal performance for all users. These include:

**1. Burst Limits (Concurrency Limits)**

Concurrency limits control how many simultaneous API calls can be processed at once. This prevents a single user from overwhelming the system, especially during peak usage.

**2. Base rate limits per Key/User**

Every API key has a base rate limit, typically measured in requests per second or minute. That depends on the user’s subscription plan. These may also include credit-based limits for specific products like the Market Data REST API.

**3. Special endpoint restrictions**

Certain protocols or endpoints (e.g., FIX, WebSocket) have unique limits. For example:

* **WebSocket API** includes request limits per IP, hello limits, and concurrency caps.
* **FIX API** allows only one session per API key. Opening a new session disconnects the current one.

**4. Overage Options**

You can continue using CoinAPI beyond your limit by paying overage fees. This ensures uninterrupted access even during high-volume periods.

**5. Custom Limit Increases**

Some limits (like concurrency) can be increased by request. These are reviewed case-by-case basis depending on usage history and infrastructure capacity.

These layered controls help us deliver reliable performance while maintaining flexibility for advanced users.

Rate limits are built-in restrictions on how many API requests you can make in a specific time frame. These limits exist to maintain platform stability and ensure fair usage.

CoinAPI does not enforce **static tier-based rate limits** the way some providers do. Instead, we operate on an **autoscaling model.** Our infrastructure dynamically adjusts to accommodate higher usage in real time, helping avoid unnecessary throttling during legitimate spikes in volume. This is especially valuable for enterprise and high-frequency users who can’t afford hard stops.

Behind the scenes, a dedicated rate-limiting module continuously checks your request volume, matches it to your active plan, and determines whether to throttle, allow, or reject traffic. This logic ensures fairness and reliability while allowing flexibility during bursts.

CoinAPI Market Data API rate limits
-----------------------------------

CoinAPI enforces rate limits for its **Market Data API** based on your selected plan. Each tier defines how many requests (credits) your API key can make per day and what features you can access. These plans are designed to scale with your usage, from testing to enterprise-grade infrastructure.

> ⚠️ Note: CoinAPI no longer offers a "Free" tier for Market Data API. This has been replaced by the Metered (Pay-As-You-Go) model, where access depends on the availability of credits in your customer portal.

![CoinAPI Market Data API rate limits](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fc9abbc5f098932d3b0d1275e7079047c98ddf732-1290x628.png&w=1920&q=75)

📘 [For a more detailed breakdown, please visit our pricing page](https://www.coinapi.io/products/market-data-api/pricing)

Each **Market Data API key** is associated with a specific plan and throttled accordingly.

> 💡 Note: Other CoinAPI products (e.g., Exchange Rates API, Indexes API) may have different rate limits. Check product-specific docs for details.

How to monitor your API usage and quotas
----------------------------------------

While CoinAPI previously returned `X-RateLimit` headers in many HTTP responses, these headers are **not consistently available across all endpoints or products**. For reliable monitoring of your quota, the recommended approach is to use the Customer Portal.

### Customer Portal → Usage Metrics

* View your current and historical usage
* Monitor remaining daily credits
* Track overage status and billing

This method gives you **real-time visibility** into quota usage across all API keys without consuming additional credits.

> 🔗 Learn more: [Why rate limit headers may not always be shown](https://docs.coinapi.io/general/faq/api/Why-are-limit-headers-not-always-showing-on-a-request)

![Usage Metrics](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F171cb07a2632394504eee94d54b5348ad6c91e5c-3902x1832.png&w=1920&q=75)

### Types of Limits

![CoinAPI Types of Limits](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F4b86a332bfc9de20d8d9f7dadd12c0fd560ace33-1084x466.png&w=1920&q=75)

Credits and API Rate Limits in REST API Requests
------------------------------------------------

The more data you request in a single API call, the more credits it consumes, based on the `limit` parameter.

Not all REST API requests consume the same number of credits. The cost is based on **data volume**, most commonly influenced by the `limit` parameter.

Here are two examples to illustrate how this works:

![Credits and API Rate Limits in REST API Requests](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F60adb25a078064dceff0861087b92f029ee4fb54-1040x334.png&w=1920&q=75)

CoinAPI calculates usage by summing the total **credit consumption** across your calls. The more data you request in a single call, the more credits it consumes.

How CoinAPI measures API usage
------------------------------

At CoinAPI, a "request" is defined by the **amount of data you're asking for**, not necessarily how many times you call the API.

* If your API call **doesn't include a `limit` parameter** or the endpoint doesn't support it, then the call is counted as **one request** by default.
* If your call **uses the `limit` parameter**, then the system counts **one request for every 100 data points you ask for**.

**Examples:**

* A call with `limit=200` counts as **2 requests**
* A call with `limit=500` counts as **5 requests**

This model ensures a fair billing system, especially for requests that return large volumes of data in a single response.

> 🧠 Note: This logic applies primarily to REST API calls. WebSocket usage is measured differently, based on subscription volume and message frequency.

This approach ensures fair usage measurement, especially for large data pulls or batch requests.

📘 [View API Limits & Billing Metrics →](https://docs.coinapi.io/naas-api/api-limits-and-billing-metrics)

### **Credit Consumption Examples: Real API Calls and Costs**

Understanding credit consumption can be confusing. Here are real examples showing exactly how CoinAPI calculates credits for common API calls:

#### **OHLCV Historical Data Examples**

**Example 1: Single Day of 1-Minute Data**

bashGET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/history?period\_id=1MIN&time\_start=2024-01-01T00:00:00&time\_end=2024-01-02T00:00:00 # Returns: 1440 data points (24 hours × 60 minutes) # Credits used: 14.4 → rounded up to 15 credits

**Example 2: One Week of Hourly Data**

bashGET /v1/ohlcv/COINBASE\_SPOT\_ETH\_USD/history?period\_id=1HRS&time\_start=2024-01-01&time\_end=2024-01-08 # Returns: 168 data points (7 days × 24 hours) # Credits used: 1.68 → rounded up to 2 credits

**Example 3: Large Historical Query**

bashGET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/history?period\_id=1MIN&time\_start=2024-01-01&time\_end=2024-01-31 # Returns: ~44,640 data points (31 days × 1440 minutes) # Credits used: 446.4 → rounded up to 447 credits

#### **Date Parameter Special Rule: 10 Credit Maximum**

**Important:** When using date-bounded queries (with `time_start` and `time_end`), CoinAPI caps credit consumption at **10 credits maximum** per request, regardless of data volume returned.

**Example:**

bashGET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/history?period\_id=1MIN&time\_start=2024-01-01&time\_end=2024-12-31 # Returns: ~525,600 data points (full year of minutes) # Normal calculation: 5,256 credits # Actual charge: 10 credits (capped)

#### **Current Data vs Historical Data**

**Current/Latest Data (No Date Parameters):**

bashGET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/latest?period\_id=1DAY&limit=100 # Returns: 100 data points # Credits used: 1 credit (100 data points = 1 credit)

**Latest Data with Higher Limit:**

bashGET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/latest?period\_id=1DAY&limit=3000 # Returns: 3000 data points # Credits used: 30 credits (3000 ÷ 100 = 30)

#### **Trade Data Examples**

**Recent Trades:**

bashGET /v1/trades/BINANCE\_SPOT\_BTC\_USDT/latest?limit=1000 # Returns: 1000 trade records # Credits used: 10 credits

**Historical Trades (Date-Bounded):**

bashGET /v1/trades/BINANCE\_SPOT\_BTC\_USDT/history?time\_start=2024-01-01&time\_end=2024-01-02 # Returns: Potentially 50,000+ trades # Credits used: 10 credits (date-bounded cap)

#### **Common Misconceptions Clarified**

**❌ Wrong Assumption:** "Each API call = 1 credit" **✅ Reality:** Credits depend on data volume returned

**❌ Wrong Assumption:** "If I make 5 API calls, I use 5 credits" **✅ Reality:** 5 calls returning 100 data points each = 5 credits total

**❌ Wrong Assumption:** "Historical queries are always expensive" **✅ Reality:** Date-bounded queries are capped at 10 credits maximum

**❌ Wrong Assumption:** "limit=1000 always costs 10 credits" **✅ Reality:** Only if the endpoint actually returns 1000 data points

#### **Order Book Snapshot Examples**

**Single Symbol Order Book:**

bashGET /v1/orderbooks/BINANCE\_SPOT\_BTC\_USDT/current # Returns: 1 snapshot (top 20 levels) # Credits used: 1 credit

**Note:** Order book endpoints don't support multi-symbol queries, so each symbol requires a separate request.

#### **Credit Optimization Strategies**

**Strategy 1: Use Date Boundaries for Large Historical Queries**

bash# Instead of: GET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/latest?limit=10000 # 100 credits # Use: GET /v1/ohlcv/BINANCE\_SPOT\_BTC\_USDT/history?time\_start=2024-01-01&time\_end=2024-01-31 # 10 credits

**Strategy 2: Batch Multiple Days in Single Request**

bash# Efficient: One request for full month GET /v1/trades/BINBASE\_SPOT\_BTC\_USDT/history?time\_start=2024-01-01&time\_end=2024-02-01 # 10 credits # Inefficient: 31 separate daily requests # 31 × 10 credits = 310 credits for the same data

#### **Monitoring Your Credit Usage**

**Check Response Headers:**

httpHTTP/1.1 200 OK X-Credits-Used: 15 X-Credits-Remaining: 985

**Best Practice:** Always monitor the `X-Credits-Used` header to understand actual consumption patterns for your specific use cases.

Optimizing REST API usage with Credit-Based limits
--------------------------------------------------

CoinAPI’s REST API uses a **credit-based billing model**, where requests are billed based on the **volume of data retrieved**, not just the number of calls.

* A **single-symbol trade request** (default `limit=100Consumes` **1 credit**.
* A request with a higher `limit`, like `limit=1000`would consume **10 credits**.

> 🔎 Note: The order book endpoint does not support multi-symbol queries. Separate requests must be made for each symbol.

To optimize your usage:

* Use the `limit` parameter wisely to batch requests when appropriate
* Monitor the `x-credits-used` Response header to understand the cost per call

![Optimizing REST API Usage with Credit-Based Limits](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb1c6fd23d4a9d2360cfaf80ed59f203bddcc5907-1016x296.png&w=1920&q=75)

### Common Triggers for Limit Errors

![Common Triggers for Limit Errors](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fdd35a015e1dff52f380c5db7a7a437f2c845405e-1118x452.png&w=1920&q=75)

**Example addition under “Special Endpoint Restrictions”:**

For example, the Market Data WebSocket API includes

* Max 10 connections per IP
* Max 1000 messages/second per connection
* Max 1000 `hello` messages/day per IP

The FIX API supports 1 session per API key — opening a new session will disconnect the current one.

How to monitor API rate limits without exceeding them?
------------------------------------------------------

The best method is to use the **Customer Portal Metrics tab**. It provides real-time insights into your API usage and remaining quota **without consuming any credits or impacting rate limits**.

This is especially useful for:

* Monitoring across multiple keys
* Usage alerts for automated systems
* Budgeting API use in high-volume production environments

If you do use the response headers:

* Note that not all endpoints consistently include them
* You’ll still be consuming quota by making the call

For full transparency and control, the Customer Portal remains the most efficient and quota-free option.

Example of usage limits at Customer Portal:

![ ](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fcf261f9e8e6ad4f98e833ef42a0effbf65d84b61-2018x490.png&w=1920&q=75)

What happens if I exceed my API rate limits with CoinAPI?
---------------------------------------------------------

**Step 1: Check What Limit You Hit**

Use the CoinAPI dashboard or check API response headers. Common codes:

* `429 Too Many Requests` (rate limit)
* `403 Forbidden` (quota exceeded or unsupported feature)

**Step 2: Adjust and Retry**

Back off temporarily. Refactor with smarter retry/cache logic.

**Step 3: Talk to CoinAPI**

Need higher throughput? We're here to help with:

* Troubleshooting quota usage
* Temporary quota increases
* Tailored plans for enterprise use cases

Tier 1: 10,000 req/day → 50 USD/month

• Tier 2: 50,000 req/day → 150 USD/month

(*Example only — contact sales for live pricing*)

📨 [How to upgrade/downgrade my subscription? →](https://docs.coinapi.io/general/faq/billing-and-subscriptions/How-to-upgrade-downgrade-my-subscription)

How do I request a CoinAPI quota increase?
------------------------------------------

If you're running high-volume queries, handling many tokens across multiple exchanges, or backfilling months of historical data, it’s normal to wonder:

* *What happens if I exceed my plan?*
* *Will I be throttled, or just billed more?*
* *Can I predict my usage and control costs?*

Here’s how CoinAPI handles that:

✅ **Transparent overage policy** – You can keep building beyond your plan's quota by paying a predictable per-unit fee. No hard blocks.

✅ **Real-time monitoring** – Use the `X-RateLimit` headers and dashboard insights to track usage across keys and projects.

✅ **Custom plans** – We work with scaling teams to adjust concurrency limits, historical data access, and volume thresholds.

### How do I request a CoinAPI quota increase?

Contact our sales team at [CoinAPI Sales](https://www.coinapi.io/contact-us) for custom plans tailored to your needs.

### TL;DR

Understanding your API rate limits is key to avoiding disruptions. You don’t need to stop building when you hit your quota, you just need better visibility, smarter tooling, or the right plan.

* Track your API rate limits dynamically with CoinAPI’s customer portal
* REST API uses credits; the cost varies by request size
* Use overage options to avoid hard stops
* Contact CoinAPI for custom scaling

If you're:

* Backfilling historical data for research
* Running real-time models on multiple tokens
* Scaling a cross-exchange trading system

CoinAPI scales with you.

👉 [Talk to us about volume pricing](https://www.coinapi.io/contact-us)

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