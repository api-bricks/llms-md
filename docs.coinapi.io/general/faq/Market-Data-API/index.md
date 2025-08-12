Market Data API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/Market-Data-API/)

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

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [FAQ](/general/faq/)

  + [General](/general/faq/general/)
  + [API Usage and Limits](/general/faq/API-Usage-and-Limits/)
  + [Billing, Payment, and Subscriptions](/general/faq/Billing-Payment-and-Subscriptions/)
  + [Account Management](/general/faq/Account-Management/)
  + [Security and Privacy](/general/faq/Security-and-Privacy/)
  + [API Access & Integration](/general/faq/API-Access-and-Integration/)
  + [Market Data API](/general/faq/Market-Data-API/)
  + [EMS Trading API](/general/faq/EMS-Trading-API/)
  + [Indexes API](/general/faq/Indexes-API/)
  + [Flat Files API](/general/faq/Flat-Files-API/)
  + [Exchange Rates API](/general/faq/Exchange-Rates-API/)
  + [Node as a Service](/general/faq/Node-as-a-Service/)
  + [Enterprise Plan](/general/faq/Enterprise-Plan/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [FAQ](/general/faq/)
* Market Data API

On this page

Market Data API
===============

Welcome to the CoinAPI FAQ. We've grouped the most common customer questions by product to help you find quick, clear answers.

Tips for Navigating This FAQ[​](/general/faq/Market-Data-API/#tips-for-navigating-this-faq "Direct link to Tips for Navigating This FAQ")
-----------------------------------------------------------------------------------------------------------------------------------------

* Use CTRL+F to search for terms like "order book", "Flat Files", or "credits".
* Bookmark docs.coinapi.io for full technical documentation.

Frequently Asked Questions[​](/general/faq/Market-Data-API/#frequently-asked-questions "Direct link to Frequently Asked Questions")
-----------------------------------------------------------------------------------------------------------------------------------

### 1. Do crypto exchanges send duplicate trade data messages?[​](/general/faq/Market-Data-API/#1-do-crypto-exchanges-send-duplicate-trade-data-messages "Direct link to 1. Do crypto exchanges send duplicate trade data messages?")

Yes, some exchanges occasionally send trade data with duplicate timestamps and prices. CoinAPI doesn’t filter these but includes a unique *guid* per trade so you can identify and deduplicate them easily in your system.

### 2. Can historical order books reconstructed from L2 updates be crossed (bid-ask overlap) occasionally?[​](/general/faq/Market-Data-API/#2-can-historical-order-books-reconstructed-from-l2-updates-be-crossed-bid-ask-overlap-occasionally "Direct link to 2. Can historical order books reconstructed from L2 updates be crossed (bid-ask overlap) occasionally?")

Yes. Historical L2 order books can occasionally show crossed spreads (bid ≥ ask) due to how some exchanges queue and match orders. These overlaps reflect the raw data as received and may result from internal exchange engine design or update timing.

### 3. Do you collect order books as snapshots or in streaming mode?[​](/general/faq/Market-Data-API/#3-do-you-collect-order-books-as-snapshots-or-in-streaming-mode "Direct link to 3. Do you collect order books as snapshots or in streaming mode?")

We collect order book data in both formats:

* Snapshot mode: Get static limit order book snapshots for specific points in time, ideal for backtesting and historical analysis.
* Streaming mode: Access real-time order book updates via our WebSocket feed for live trading and monitoring.

### 4. Do you offer historical crypto futures market data?[​](/general/faq/Market-Data-API/#4-do-you-offer-historical-crypto-futures-market-data "Direct link to 4. Do you offer historical crypto futures market data?")

Yes, CoinAPI offers historical data for crypto futures across major derivatives exchanges like Binance Futures, Bybit, BitMEX, Deribit, OKX, and more. This includes contract specs, prices, volumes, and open interest. Ideal for backtesting and analytics.

### 5. Do you provide historical options data?[​](/general/faq/Market-Data-API/#5-do-you-provide-historical-options-data "Direct link to 5. Do you provide historical options data?")

Yes, CoinAPI offers historical options data from exchanges like Deribit and Binance. This includes strike prices, expiration dates, implied volatility, and trading volumes. Data is available via REST API and Flat Files for options market analysis, backtesting, and strategy development.

[View our historical data documentation](https://docs.coinapi.io/market-data/rest-api/trades/historical-data)

### 6. Do you provide market data in a normalized format?[​](/general/faq/Market-Data-API/#6-do-you-provide-market-data-in-a-normalized-format "Direct link to 6. Do you provide market data in a normalized format?")

Yes, CoinAPI delivers all market data in a fully normalized format. This means the structure, field names, and data conventions are standardized across all supported exchanges and providers.

Normalization ensures:

* Consistent data structure regardless of exchange origin
* Easier integration and parsing
* Reduced risk of errors due to inconsistent formats

Whether you're consuming trades, quotes, OHLCV, or order book data, the format remains unified—so your application logic doesn't have to account for exchange-specific differences.

This is particularly useful for multi-exchange trading systems, analytics, or historical data aggregation.

For technical details, see:

<https://docs.coinapi.io/market-data>

### 7. Do you provide time-based Order Book aggregated data (e.g., OHLCV or interval-based snapshots)?[​](/general/faq/Market-Data-API/#7-do-you-provide-time-based-order-book-aggregated-data-eg-ohlcv-or-interval-based-snapshots "Direct link to 7. Do you provide time-based Order Book aggregated data (e.g., OHLCV or interval-based snapshots)?")

CoinAPI specializes in high-resolution, tick-level historical Order Book data for all supported cryptocurrency exchanges. Currently, our APIs (REST and Flat Files) deliver raw tick-level Order Book data only and do not offer native support for time-based aggregated data such as OHLC or interval-based order book snapshots.

However, if you're looking for Order Book time-aggregated data:

* You can generate it client-side using our SDKs or data processing tools
* Libraries in our GitHub repository include functions to build OHLCV and similar datasets from raw order book data.

This approach gives you full control over the granularity, aggregation intervals, and custom logic applied during processing.

For SDKs and examples, visit:

<https://github.com/api-bricks/api-bricks-sdk>

### 8. How are order book data snapshots provided?[​](/general/faq/Market-Data-API/#8-how-are-order-book-data-snapshots-provided "Direct link to 8. How are order book data snapshots provided?")

CoinAPI provides order book snapshots through both the HTTP API and downloadable flat files, depending on your use case and required granularity.

Available snapshot methods:

1. Daily Snapshots via HTTP API
   * Historical order book data includes a snapshot at 00:00 UTC each day
   * Useful for daily reference points or position marking
2. Custom Snapshots via Client Libraries
   * You can generate custom order book snapshots at any desired interval (milliseconds, seconds, minutes, hours)
   * These are computed client-side using raw tick-level data (trades, quotes, book changes) obtained from the HTTP API
   * Supported in our open-source client libraries
3. Flat Files / CSV Downloads
   * Tick-by-tick order book data and snapshots are available as downloadable files
   * Ideal for large-scale historical analysis, backtesting, and local storage

This approach gives you flexibility to work with lightweight snapshots for fast lookup or reconstruct detailed order books with full depth for precise modeling.

### 9. How does the full orderbook stream work?[​](/general/faq/Market-Data-API/#9-how-does-the-full-orderbook-stream-work "Direct link to 9. How does the full orderbook stream work?")

CoinAPI delivers full order book data via the WebSocket API using a combination of snapshots and incremental updates. To maintain accurate state, follow this process:

1. Initial Snapshot

   When you subscribe to the order book, the first message you receive will have `is_snapshot = true`. This contains the full depth of the order book and should be used to initialize your local book.
2. Apply Updates

   Once the snapshot is processed, apply all subsequent messages with `is_snapshot = false` to maintain the real-time state.
3. Mid-Connection Snapshots

   If you receive another snapshot while already connected (another `is_snapshot = true`), invalidate your current book state and replace it with the new snapshot to stay in sync.

This approach ensures that your order book is always consistent, even in cases of reconnection or partial data loss.

### 10. How historical raw market data is being sourced?[​](/general/faq/Market-Data-API/#10-how-historical-raw-market-data-is-being-sourced "Direct link to 10. How historical raw market data is being sourced?")

CoinAPI sources historical raw market data directly from exchange infrastructure using the most efficient methods available:

* Primary Source – WebSocket APIs

  When available, real-time data is ingested from exchange WebSocket feeds, which offer high-frequency, low-latency access to trades, quotes, and order book updates.
* Fallback – REST APIs

  For exchanges or data types not supported via WebSocket, CoinAPI uses periodic polling of REST APIs to ensure continuous data coverage.

This combination ensures that even in cases where exchanges offer limited protocols, CoinAPI still collects and stores the most complete raw dataset possible for historical access.

### 11. How much historical data does CoinAPI have?[​](/general/faq/Market-Data-API/#11-how-much-historical-data-does-coinapi-have "Direct link to 11. How much historical data does CoinAPI have?")

CoinAPI provides one of the most comprehensive archives of cryptocurrency market data available, with records dating back to:

* Start Date: 2014-02-24 17:43:05.0000000
* Earliest Source: Data collection began during the Mt. Gox era

This historical dataset includes tick-level trades, quotes, and order book data (where available), and is continuously expanded across hundreds of supported exchanges.

### 12. How much historical data can I fetch from a single query?[​](/general/faq/Market-Data-API/#12-how-much-historical-data-can-i-fetch-from-a-single-query "Direct link to 12. How much historical data can I fetch from a single query?")

The volume of historical data you can retrieve in a single API request depends on several factors:

1. Endpoint-Specific Limits

   Most endpoints support a `limit` parameter that controls how many records you can request. For example, REST API endpoints typically allow up to 100,000 data points per request.
2. Subscription Plan Constraints

   Your plan may include restrictions on the number of requests per day or the rate of requests. Higher-tier plans support greater throughput.
3. Pagination and Rate Limiting

   If you need more data than a single request allows, use pagination by issuing sequential requests with adjusted `time_start` and `time_end` parameters. Be mindful of rate limits to avoid throttling (HTTP 429).
4. Data Type and Granularity

   Endpoints like OHLCV with high granularity (e.g., 1-second intervals) return more records than those at hourly or daily intervals. This affects how much time range fits within the maximum `limit`.

### 13. What data types do you support?[​](/general/faq/Market-Data-API/#13-what-data-types-do-you-support "Direct link to 13. What data types do you support?")

CoinAPI provides a wide range of cryptocurrency market data types, designed to support everything from real-time trading to historical analytics. Available data types include:

* Trade Data – Executed transactions with price, size, and timestamp
* Order Book Data
  + Level 1 (L1) – Best bid and ask (Quotes)
  + Level 2 (L2) – Full depth of visible orders
  + Level 3 (L3) – Individual order-level data (where available)
* Quotes – Best Bid and Asks
* OHLCV – Time-aggregated Open, High, Low, Close, Volume metrics
* Metrics - Quantitative measurements used to evaluate the performance and activity of cryptocurrency exchanges.
* Exchange Rates - Last 24 hour (rolling window over time) Volume Weighted Average Price across multiple data sources listed on our platform.

This rich dataset powers a wide range of use cases, including algorithmic trading, compliance monitoring, and market research.

### 14. What does high frequency historical data mean?[​](/general/faq/Market-Data-API/#14-what-does-high-frequency-historical-data-mean "Direct link to 14. What does high frequency historical data mean?")

High frequency historical data refers to tick-level market data collected and stored at the maximum granularity that each exchange's real-time WebSocket feed allows.

Key points:

* Tick-level granularity includes individual trades, order book updates, and quote changes
* Granularity varies by exchange, depending on the capabilities and limitations of their APIs
* For some exchanges, high frequency may capture multiple updates per millisecond, while others may be limited to 1-second or slower intervals

CoinAPI ensures that all data is collected at the highest possible resolution to support use cases like backtesting, market microstructure analysis, and algorithmic strategy development.

### 15. What is the difference between futures and perpetual swaps contracts?[​](/general/faq/Market-Data-API/#15-what-is-the-difference-between-futures-and-perpetual-swaps-contracts "Direct link to 15. What is the difference between futures and perpetual swaps contracts?")

The main difference lies in expiration and price alignment mechanisms:

* Futures Contracts
  + Have a fixed expiration date (e.g., quarterly or monthly)
  + Price typically converges toward the spot price as the contract nears expiry
  + Used for hedging, speculation, and arbitrage over defined timeframes
* Perpetual Swap Contracts (aka "perps", "swaps", or "perpetual futures")
  + Have no expiration date
  + Use funding rates to align their price with the spot market
  + Funding is exchanged between long and short positions periodically (e.g., every 8 hours)

Both instruments are supported by CoinAPI and follow different symbol ID patterns in our system.

### 16. What can L2 order book data be used for?[​](/general/faq/Market-Data-API/#16-what-can-l2-order-book-data-be-used-for "Direct link to 16. What can L2 order book data be used for?")

L2 (Level 2) order book data, also known as market-by-price, provides aggregated bids and asks at each price level. This data enables deeper market analysis beyond the top-of-book and is commonly used to:

* Measure order book imbalance — compare total bid vs ask volume
* Estimate average execution cost — especially for larger orders across multiple price levels
* Evaluate liquidity away from the midpoint — understand how deep the book is beyond best bid/ask
* Track average spread — monitor bid-ask dynamics over time
* Detect hidden interest — identify patterns suggestive of iceberg orders or spoofing behavior

L2 data is essential for traders, quants, and researchers conducting microstructure analysis, slippage modeling, or execution strategy backtesting.

### 17. What can L3 order book data be used for?[​](/general/faq/Market-Data-API/#17-what-can-l3-order-book-data-be-used-for "Direct link to 17. What can L3 order book data be used for?")

L3 (Level 3) order book data, or market-by-order, includes granular event-level data such as:

* Individual order additions
* Modifications
* Cancellations
* Matches (executions)

This detailed view of the order book enables advanced analysis, including:

* Order resting time — measure how long orders remain unfilled
* Order fill probability — estimate execution likelihood based on position in queue
* Queue dynamics — analyze how the order queue evolves, including cancellations and re-prioritization

L3 data is essential for high-frequency trading, order flow modeling, latency-sensitive strategy development, and regulatory research. L3 is only available for selected exchanges: BITSO and COINBASE.

### 18. What metrics does CoinAPI use to evaluate cryptocurrency exchange performance and activity?[​](/general/faq/Market-Data-API/#18-what-metrics-does-coinapi-use-to-evaluate-cryptocurrency-exchange-performance-and-activity "Direct link to 18. What metrics does CoinAPI use to evaluate cryptocurrency exchange performance and activity?")

CoinAPI monitors a wide range of quantitative and structural metrics to evaluate exchange performance, market health, and trading activity. These include:

* Trading volume — measures liquidity and overall activity
* Market depth — assesses available liquidity at various price levels
* Order book analysis — evaluates book imbalance, quote updates, and order concentration
* Spread calculation — tracks bid-ask spread efficiency across trading pairs
* Price chart interpretation — uses OHLCV data to generate price movement insights
* Market capitalization — reflects relative value across assets and exchanges
* Trading pairs evaluation — reviews the diversity and liquidity of listed pairs
* User metrics analysis — proxy indicators like volume per user or active asset ratios (when available)
* Trading fees overview — considers cost structures that impact trade behavior
* Security metrics — evaluates exchange trustworthiness based on uptime, incidents, and API stability

These metrics are used internally to assess data quality and externally by clients for analytics, modeling, and exchange benchmarking.

### 19. Why does the data source matter, and why does CoinAPI use real-time WebSocket feeds instead of relying on REST endpoints?[​](/general/faq/Market-Data-API/#19-why-does-the-data-source-matter-and-why-does-coinapi-use-real-time-websocket-feeds-instead-of-relying-on-rest-endpoints "Direct link to 19. Why does the data source matter, and why does CoinAPI use real-time WebSocket feeds instead of relying on REST endpoints?")

The choice of data source significantly impacts data quality, granularity, and analytical value. CoinAPI prioritizes real-time WebSocket feeds as the primary method of data collection for the following reasons:

* Maximum Granularity

  WebSocket APIs provide tick-level updates, including every trade, quote change, and order book update—data often not available through REST endpoints.
* Market Microstructure Visibility

  Real-time streams capture sub-second price movements, queue shifts, and order flow dynamics, enabling in-depth analysis and modeling.
* Lower Latency & Real-Time Delivery

  WebSocket connections push data as events happen, without the polling delays inherent in REST APIs.
* Richer Event Coverage

  Certain events—like order cancellations or depth changes—may be entirely missing from REST APIs but are visible via WebSocket.

While WebSocket feeds can be more fragile (e.g., occasional disconnects or exchange-side issues), they provide a more complete and real-time view of market behavior, which is essential for algorithmic trading, research, and high-frequency applications.

### 20. Why is the `volume_1day_usd` value for BTC or ETH higher than on platforms like CoinGecko?[​](/general/faq/Market-Data-API/#20-why-is-the-volume_1day_usd-value-for-btc-or-eth-higher-than-on-platforms-like-coingecko "Direct link to 20-why-is-the-volume_1day_usd-value-for-btc-or-eth-higher-than-on-platforms-like-coingecko")

The `volume_1day_usd` value from CoinAPI’s `/v1/assets` endpoint represents the aggregated 24-hour trading volume across all supported market types, including:

* Spot markets (SPOT)
* Perpetual contracts (PERPETUAL)
* Futures contracts (FUTURES)
* Options (OPTIONS)

In contrast, platforms like CoinGecko typically report spot-only volume, which results in significantly lower totals. CoinAPI’s broader aggregation provides a more complete picture of an asset's true liquidity and trading activity.

Additional Tips:

* This behavior is not impacted by your subscription tier. It applies even on the free or trial plans.
* If you need volume segmented by market type, use the `/v1/ohlcv`, `/v1/exchangerate`, or `/v1/symbols` endpoints and filter by instrument type or exchange.

### 21. Why am I receiving multiple OHLCV updates for the same time window via WebSocket?[​](/general/faq/Market-Data-API/#21-why-am-i-receiving-multiple-ohlcv-updates-for-the-same-time-window-via-websocket "Direct link to 21. Why am I receiving multiple OHLCV updates for the same time window via WebSocket?")

This is expected behavior. CoinAPI's WebSocket stream sends incremental OHLCV updates for the currently open time interval to provide real-time accuracy as new trades arrive.

Key points:

* Multiple messages may be delivered for the same time window (e.g., 15-second, 1-minute interval)
* These updates share the same `time_period_start` and `time_period_end` timestamps
* Each message reflects an updated aggregation of OHLCV metrics as new data enters the system
* Once the interval ends, a final update is sent to indicate the closed candle

If you need only finalized OHLCV values:

Use the REST API `/ohlcv/latest` endpoint, which returns the most recent completed (closed) candles per symbol and period.

### 22. Can I retrieve time-aggregated order book data using `period_id` from the REST API?[​](/general/faq/Market-Data-API/#22-can-i-retrieve-time-aggregated-order-book-data-using-period_id-from-the-rest-api "Direct link to 22-can-i-retrieve-time-aggregated-order-book-data-using-period_id-from-the-rest-api")

No, the `period_id` parameter is not supported on the `/v1/orderbooks/{`symbol\_id`}/history` endpoint.

Why:

* Order book data is event-driven, not time-based.
* Updates are pushed whenever there's a change in market depth—not at regular intervals like 1-minute or 5-minute periods.
* As a result, CoinAPI does not provide time-aggregated order book snapshots (e.g., OHLCV-style summaries for bids/asks) via REST API.

Instead, the endpoint returns a chronological sequence of raw snapshots and depth updates, allowing you to reconstruct the order book state over time.

If you need time-aggregated depth views, you can:

* Build custom snapshots client-side by aggregating raw order book data
* Use CoinAPI’s Flat Files for efficient historical order book processing at scale

### 23. Why is the `/v1/orderbooks/{`symbol\_id`}/history` endpoint slow for symbols like `BINANCE_SPOT_BTC_USDT`?[​](/general/faq/Market-Data-API/#23-why-is-the-v1orderbookssymbol_idhistory-endpoint-slow-for-symbols-like-binance_spot_btc_usdt "Direct link to 23-why-is-the-v1orderbookssymbol_idhistory-endpoint-slow-for-symbols-like-binance_spot_btc_usdt")

This endpoint may respond slowly for high-volume symbols like `BINANCE_SPOT_BTC_USDT` due to the massive number of order book updates that occur throughout the day.

Reasons for slower response:

* The system must read the entire day's data (from 00:00 to 23:59 UTC) before generating a response, regardless of the specific time slice you're interested in.
* The `time_start` parameter has been deprecated, and you are encouraged to specify only the `date` parameter for full-day queries.
* This approach ensures data consistency and completeness, especially for reconstructing accurate order book states.

Best practice:

* Download the entire daily dataset
* Store and filter locally for performance and scalability
* Use CoinAPI’s Flat Files product if you require large-scale, efficient historical processing

### 24. Does CoinAPI provide data for blockchain verification, deposit/withdrawal status, or token contract addresses?[​](/general/faq/Market-Data-API/#24-does-coinapi-provide-data-for-blockchain-verification-depositwithdrawal-status-or-token-contract-addresses "Direct link to 24. Does CoinAPI provide data for blockchain verification, deposit/withdrawal status, or token contract addresses?")

CoinAPI primarily provides market data — such as `ask_price`, `bid_price`, `volume`, and symbol metadata — but also offers extended blockchain insights through the Node as a Service (NaaS) platform.

Here’s how your use cases are supported:

1. Verifying Blockchain and Token Details

* The `/v1/assets` endpoint in the Market Data API provides metadata such as `chain_id`, `network_id`, and blockchain asset identifiers.
* For more advanced token-level verification (e.g., contract inspection), CoinAPI's Node as a Service supports blockchain queries, especially for Ethereum and EVM-compatible chains.

2. Deposit and Withdrawal Availability

* CoinAPI does not currently provide real-time availability of deposits/withdrawals for assets on exchanges.
* This status usually requires direct API access or scraping of each exchange’s operational notices.

3. Deposit/Withdraw Address Validation

* Not available directly via CoinAPI.
* However, NaaS Ethereum methods can retrieve blockchain transaction data, which can assist in indirectly verifying address activity and correctness.

4. Token Contract Address Verification

* Use `/v1/assets` for active asset metadata.
* Use `/v1/symbols` to map tokens to specific exchanges, with `symbol_id_exchange` and related metadata.

### 25. Does CoinAPI provide aggregated Kline, order book, trades, or market sentiment data across multiple exchanges?[​](/general/faq/Market-Data-API/#25-does-coinapi-provide-aggregated-kline-order-book-trades-or-market-sentiment-data-across-multiple-exchanges "Direct link to 25. Does CoinAPI provide aggregated Kline, order book, trades, or market sentiment data across multiple exchanges?")

CoinAPI primarily provides exchange-specific market data for transparency and granularity. Here's how aggregation works across different data types:

Kline (OHLCV), Order Book, and Trades:

* These datasets are not aggregated across exchanges
* Data is available per symbol and per exchange, such as `BINANCE_SPOT_BTC_USDT` or `COINBASE_SPOT_ETH_USD`
* If you need aggregated views, you'll need to implement that logic on your end

Aggregated Exchange Rates:

* The Exchange Rates API is an exception
* It provides volume-weighted average prices (VWAP) across multiple venues, delivering an accurate and blended view of the market
* Ideal for fair pricing, reporting, and portfolio valuation

Market Sentiment:

* For macro-level insights, use the Indexes API
* It aggregates news, social signals, and behavioral data into sentiment indicators and thematic indexes

### 26. Do you provide OHLC, turnover, trades, market cap for perpetuals, or funding rate data?[​](/general/faq/Market-Data-API/#26-do-you-provide-ohlc-turnover-trades-market-cap-for-perpetuals-or-funding-rate-data "Direct link to 26. Do you provide OHLC, turnover, trades, market cap for perpetuals, or funding rate data?")

Here’s what’s available through CoinAPI:

OHLCV & Trades

* Yes — CoinAPI provides OHLCV (Kline) data based on the Trades dataset.
* Access via: `/v1/ohlcv/{`symbol\_id`}/history`
* Raw trades are available through: `/v1/trades`

Turnover

* Not directly provided as a standalone metric.
* However, you can calculate turnover manually using the price × volume from trade records.

Market Capitalization

* Not available by default.
* However, total supply (`SUPPLY_TOTAL`) for Ethereum tokens is available via the Metrics API, which can assist in computing market cap.

Funding Rates

* Yes — Funding rate data is available via the Metrics API for select exchanges.

### 27. Why am I only seeing SPOT symbols at `/v1/symbols`? How can I get PERP data?[​](/general/faq/Market-Data-API/#27-why-am-i-only-seeing-spot-symbols-at-v1symbols-how-can-i-get-perp-data "Direct link to 27-why-am-i-only-seeing-spot-symbols-at-v1symbols-how-can-i-get-perp-data")

If you're using the `/v1/symbols` endpoint and only receiving SPOT market data, it's likely due to not filtering by the correct `exchange_id`.

To access PERP (perpetual futures) symbols from Binance:

Use these specific `exchange_id` values:

* `BINANCEFTS` → Binance USD-M Futures (e.g., USDT-margined contracts)
* `BINANCEFTSC` → Binance COIN-M Futures (e.g., BTC-margined contracts)

You can append filters or parse your results accordingly to isolate PERP instruments from these exchanges.

Need to explore all supported exchanges?

Use the `/v1/exchanges` endpoint

### 28. How much data would I use tracking real-time prices for 100 coins, updated 24 times per day?[​](/general/faq/Market-Data-API/#28-how-much-data-would-i-use-tracking-real-time-prices-for-100-coins-updated-24-times-per-day "Direct link to 28. How much data would I use tracking real-time prices for 100 coins, updated 24 times per day?")

It’s difficult to provide an exact estimate of real-time data usage due to high variability in trading activity and exchange behavior. Here’s why:

Key Variables That Affect Usage:

* Asset Activity: Some cryptocurrencies trade constantly, others may stay idle for hours.
* Exchange Behavior: Update frequency varies — some exchanges push updates every millisecond, others less frequently.
* Market Conditions: Volatile periods or major announcements can spike activity and data volume.
* Update Type: Prices, quotes, and order book changes all have different data sizes.

Even with 100 coins and 24 updates/day, actual data usage can fluctuate significantly depending on market dynamics.

Recommendation:

Start with the Pay-as-You-Go (metered) plan. Monitor your real-world usage, and if your needs grow or stabilize, consider switching to a fixed subscription for better predictability and savings.

### 29. Why does the `/v1/symbols` endpoint time out when I try to load all symbol metadata?[​](/general/faq/Market-Data-API/#29-why-does-the-v1symbols-endpoint-time-out-when-i-try-to-load-all-symbol-metadata "Direct link to 29-why-does-the-v1symbols-endpoint-time-out-when-i-try-to-load-all-symbol-metadata")

The `/v1/symbols` endpoint contains a very large dataset, covering all active markets across hundreds of exchanges. This can lead to timeouts, especially if your client or tool has a strict timeout setting.

Workarounds & Optimization:

To reduce the response size and avoid timeouts:

* Use filtering parameters:
  + `filter_exchange_id`
  + `filter_symbol_id`
  + `filter_asset_id`

Example:

```
plaintext  
  
https://rest.coinapi.io/v1/symbols?filter_exchange_id=BINANCE
```

This retrieves only the symbols from Binance, significantly reducing data load and response time.

Pro Tip:

If you're only using symbols to validate requests, pre-filter to just the exchanges or assets you're actively integrating with. This ensures faster responses and less overhead.

### 30. Do I need to send an unsubscribe message before closing a WebSocket connection?[​](/general/faq/Market-Data-API/#30-do-i-need-to-send-an-unsubscribe-message-before-closing-a-websocket-connection "Direct link to 30. Do I need to send an unsubscribe message before closing a WebSocket connection?")

No, it is not required to send an explicit `unsubscribe` message before closing your WebSocket connection.

When you terminate a WebSocket session, the server automatically cleans up all active subscriptions. This design ensures that no data will continue to be sent after your connection is closed.

Optional: Explicit Unsubscribe

* You may still choose to send an `unsubscribe` message before disconnecting if:
  + You want clear confirmation of subscription termination
  + You manage multiple concurrent streams and need to selectively disconnect

Risk of Post-Closure Data?

* The risk of receiving residual data after closing without unsubscribing is very low.
* The server’s internal mechanisms are designed to terminate all data flows immediately upon connection close.

### 31. Can I get historical ask, bid, and order book depth data from Binance, including snapshots and real-time updates from the past year?[​](/general/faq/Market-Data-API/#31-can-i-get-historical-ask-bid-and-order-book-depth-data-from-binance-including-snapshots-and-real-time-updates-from-the-past-year "Direct link to 31. Can I get historical ask, bid, and order book depth data from Binance, including snapshots and real-time updates from the past year?")

Yes, CoinAPI provides comprehensive historical bid and ask data, including order book snapshots and top-of-book quotes from Binance and other supported exchanges.

Available Data Types:

1. Order Book (Full Limit Order Book)
   * Offers detailed historical order book snapshots and updates.
   * Ideal for reconstructing the order book at any specific timestamp.
2. Quotes
   * Provides historical best bid and ask prices.

Access Methods:

* Market Data API
  + Retrieve current and historical bid/ask and order book data using flexible REST endpoints.
  + Suitable for integration with applications needing filtered, live, or historical access.
* Flat Files API
  + Access historical market data as downloadable CSV or JSON files.
  + Ideal for backtesting, deep analysis, and bulk ingestion at scale.

Yes, you can retrieve this data for the past year (or more, depending on exchange support). Flat Files are typically best for downloading large historical datasets, while the Market Data API is ideal for application integrations and real-time updates.

### 32. How can I access historical bid/ask data and order book snapshots from Binance? Which CoinAPI product or plan should I choose?[​](/general/faq/Market-Data-API/#32-how-can-i-access-historical-bidask-data-and-order-book-snapshots-from-binance-which-coinapi-product-or-plan-should-i-choose "Direct link to 32. How can I access historical bid/ask data and order book snapshots from Binance? Which CoinAPI product or plan should I choose?")

If you're looking for detailed historical bid/ask data—including order book snapshots at specific times, CoinAPI has two key options:

Option 1: Flat Files (Best for Historical Access & Bulk Analysis)

* Full Limit Order Book (LOB) Data
  + Captures every change in the Binance order book.
  + Allows you to reconstruct the full order book at any point in time.
* Quotes Data
  + Provides top-of-book data (best bid/ask prices) over time.
  + Lightweight and efficient for quick backtests or spread analysis.

Option 2: Market Data API (For Programmatic Access)

* All predefined plans include historical and live bid/ask and order book data.
* Choose based on your preferred access protocol:
  + REST API: Good for historical and filtered data
  + WebSocket: Best for real-time streaming
  + FIX API: Ideal for institutional trading setups

Recommendation:

* Use Flat Files for downloading a complete historical dataset.
* Use Market Data API if you want to integrate real-time bid/ask data with selective historical queries into your app or trading system.

### 33. Can I retrieve aggregated liquidity data for mid-price ±X% over time intervals (e.g., 1h, 8h, 1d)?[​](/general/faq/Market-Data-API/#33-can-i-retrieve-aggregated-liquidity-data-for-mid-price-x-over-time-intervals-eg-1h-8h-1d "Direct link to 33. Can I retrieve aggregated liquidity data for mid-price ±X% over time intervals (e.g., 1h, 8h, 1d)?")

Currently, CoinAPI does not offer a direct endpoint to retrieve aggregated liquidity for mid-price ±X% over extended periods.

However, you can work around this by:

1. Using the OHLCV Historical Data endpoint to get price time series.
2. Manually calculating mid-price and defining liquidity bands (e.g., ±1%, ±5%).
3. Aggregating data over time intervals (e.g., hourly, daily) on your side.

While our Metrics endpoint provides rich market activity insights, it does not support mid-price band liquidity queries at this time.

### 34. What is the unit of `volume_1day` in the `/v1/symbols` endpoint?[​](/general/faq/Market-Data-API/#34-what-is-the-unit-of-volume_1day-in-the-v1symbols-endpoint "Direct link to 34-what-is-the-unit-of-volume_1day-in-the-v1symbols-endpoint")

The `volume_1day` field in the `/v1/symbols` endpoint represents the trading volume over the past 24 hours measured in the base asset's unit.

Example:

* For the symbol `BINANCE_SPOT_BTC_USDT`:
  + `asset_id_base` = BTC
  + So, `volume_1day` is expressed in BTC
  + Meanwhile, `volume_1day_usd` gives the same volume converted to USD

This applies to any symbol returned by the endpoint—the unit of `volume_1day` always matches the base asset of that trading pair.

Use this to distinguish between raw asset volumes and their fiat-equivalent representations.

### 35. Why am I receiving an empty response when fetching today’s historical order book data?[​](/general/faq/Market-Data-API/#35-why-am-i-receiving-an-empty-response-when-fetching-todays-historical-order-book-data "Direct link to 35. Why am I receiving an empty response when fetching today’s historical order book data?")

The `/v1/orderbooks/:symbol_id/history` endpoint does not currently support retrieving order book data for the current day. This behavior is expected, although not yet explicitly documented.

Workarounds and Real-Time Alternatives:

1. To fetch the current order book:

   Use the `GET /v1/orderbooks/:symbol_id/current` endpoint

[API Docs – Current Order Book](https://docs.coinapi.io/market-data/rest-api/order-book/get-current-order-book)

1. For real-time updates:

   Use the WebSocket API, which supports real-time streaming of order book updates.

[WebSocket Order Book Stream](https://docs.coinapi.io/market-data/websocket/messages#orderbook-l2-full--in)

Additional Notes:

* The `time_start` and `time_end` parameters are not supported for the `/current` endpoint.
* Real-time data is available, but intra-day historical data for the current day is not accessible through the historical REST endpoint at this time.
* Adding support for near-real-time historical data for the current day is on our roadmap, but we do not have a specific timeline.

Recommendation: For continuous tracking of order book data throughout the day, leverage the WebSocket API and store the data on your end for later analysis.

### 36. Why are the `X-RateLimit-Remaining` and `X-RateLimit-Reset` headers missing from the OHLCV Historical API responses?[​](/general/faq/Market-Data-API/#36-why-are-the-x-ratelimit-remaining-and-x-ratelimit-reset-headers-missing-from-the-ohlcv-historical-api-responses "Direct link to 36-why-are-the-x-ratelimit-remaining-and-x-ratelimit-reset-headers-missing-from-the-ohlcv-historical-api-responses")

In certain scenarios, CoinAPI's responses do not include the `X-RateLimit-Remaining` and `X-RateLimit-Reset` headers. This behavior is intentional to ensure fast response times and low latency. Since not all clients rely on these headers and including them can introduce performance overhead, we opt to exclude them in some cases.

Key Points:

* The `X-RateLimit-Request-Cost` header is always included, allowing you to monitor the cost of each API call.
* However, there is no way to force the inclusion of `X-RateLimit-Remaining` and `X-RateLimit-Reset` in every API response at this time.

How to Track Usage:

To monitor your API credit consumption, you can:

* Log in to the Customer Portal.
* Use the metric: Market Data API REST Credits (credits)

For more information, refer to our official documentation:

[Why limit headers are not always shown](https://docs.coinapi.io/general/faq/api/Why-are-limit-headers-not-always-showing-on-a-request)

If you have additional needs or feedback about API response headers, feel free to contact our support team.

### 37. How can I handle large result sets with the Historical OHLCV endpoint when the response doesn’t indicate total rows?[​](/general/faq/Market-Data-API/#37-how-can-i-handle-large-result-sets-with-the-historical-ohlcv-endpoint-when-the-response-doesnt-indicate-total-rows "Direct link to 37. How can I handle large result sets with the Historical OHLCV endpoint when the response doesn’t indicate total rows?")

When using the `Historical OHLCV` endpoint, the API response does not include the total number of data rows in the result set. If your dataset spans a large time range, it’s important to manually manage pagination using the `limit`, `time_start`, and `time_end` parameters.

Best Practices for Efficient Data Retrieval:

To fetch a full mnth of hourly OHLCV data (e.g., January 2025), use:

```
bash  
  
GET https://rest.coinapi.io/v1/ohlcv/BINANCE_SPOT_BTC_USDT/history?  
period_id=1HRS&  
time_start=2025-01-01T00:00:00&  
time_end=2025-02-01T00:00:00&  
limit=1000&  
output_format=csv
```

This example uses a `limit=1000`, which covers more than the 744 hours in a 31-day month. The result should include all hourly data for January 2025 in one request, provided the data exists.

Pagination Strategy:

If the time window is longer or `limit` is smaller:

* Break your time range into multiple requests using adjusted `time_start` and `time_end`.
* Use the last `time_period_end` from each response as the new `time_start` in the next request.

Credit Usage Reminder:

* Each 100 data points returned = 1 REST API credit.
* For example, fetching 800 rows will consume 8 credits, even in a single request.

For more info on API credit usage:

[Market Data API Pricing](https://www.coinapi.io/products/market-data-api/pricing)

If you have further questions or need help structuring your queries, feel free to contact our support team.

### 38. Can I connect to the main WebSocket DS endpoint from multiple environments?[​](/general/faq/Market-Data-API/#38-can-i-connect-to-the-main-websocket-ds-endpoint-from-multiple-environments "Direct link to 38. Can I connect to the main WebSocket DS endpoint from multiple environments?")

Yes, you can connect to the main WebSocket DS endpoint:

```
cpp  
  
wss://[lowercase-exchange-name].ws-ds.md.coinapi.io/
```

This connection is fully supported for use across **multiple environments**, including production, development, and staging. It allows for multiple WebSocket sessions from different IPs or systems without issue.

Additional Notes:

* This endpoint supports real-time and historical data.
* For more technical details, refer to the [WebSocket DS Documentation](https://docs.coinapi.io/market-data/websocket-ds/).

Rate Limit Reminder:

CoinAPI enforces a limit of:

* 10 hello/subscribe messages per 10 seconds.

As long as your environment respects this threshold, you can safely open multiple connections without disruption.

For further customization or troubleshooting, reach out to our support team.

### 39. How many credits are used by the OHLCV Exchanges endpoint?[​](/general/faq/Market-Data-API/#39-how-many-credits-are-used-by-the-ohlcv-exchanges-endpoint "Direct link to 39. How many credits are used by the OHLCV Exchanges endpoint?")

We define a "request" based on the amount of data you’re retrieving, not just the number of times you call the API.

* If your API call doesn’t use a `limit` parameter, or if that parameter isn’t available for the endpoint, then each API call counts as one request.
* If you use a `limit` parameter, then every 100 data points returned counts as 1 credit.

For example, if you're calling:

```
bash  
  
https://rest.coinapi.io/v1/ohlcv/exchanges/COINBASE/history?period_id=1HRS&time_start=2021-01-01&time_end=2021-01-02
```

And you receive 3,000 data points, that would consume 30 Market Data Credits (3000 / 100 = 30).

More Info:

* Learn more about [API limits and billing metrics](https://docs.coinapi.io/market-data/api-limits-and-billing-metrics)
* Review credit inclusions per plan on our [Pricing Page](https://www.coinapi.io/products/market-data-api/pricing)

If you're unsure how many credits your specific call will use, feel free to reach out to support with your query details.

### 40. Can I confirm that LMAX Digital data is available?[​](/general/faq/Market-Data-API/#40-can-i-confirm-that-lmax-digital-data-is-available "Direct link to 40. Can I confirm that LMAX Digital data is available?")

Yes, we do provide access to **LMAX Digital** data. This is available as an **add-on** that can be included with **any Market Data subscription**.

If you need assistance enabling this feature or want more details on coverage, feel free to contact our support team.

### 41. Is the datacenter located in London?[​](/general/faq/Market-Data-API/#41-is-the-datacenter-located-in-london "Direct link to 41. Is the datacenter located in London?")

Yes, CoinAPI operates a **datacenter in London**, and we automatically route you to the **closest available server** to ensure minimal latency.

If you specifically require a **London-based endpoint** with **dedicated routing** and a **latency SLA**, this is available through our **Enterprise plan** (starting at **$1260/month**). This plan includes:

* Dedicated API endpoints
* Latency SLA
* Custom routing configuration

For more details or to upgrade, please contact our support team.

### 42. Is there any delay that occurs on your end?[​](/general/faq/Market-Data-API/#42-is-there-any-delay-that-occurs-on-your-end "Direct link to 42. Is there any delay that occurs on your end?")

Our infrastructure is **optimized for low latency**, but some delays may occur depending on factors like your **geographic location**, **internet provider**, and **system configuration**.

You can easily **test the latency performance** yourself using our **free API key**, which includes **$25 in credits**—enough to experiment with various exchanges and endpoints.

If the latency you experience with the standard setup doesn’t meet your needs, consider upgrading to our **Enterprise plan**, which offers:

* **Dedicated API endpoints**
* **Latency SLA**
* **Custom routing** for optimized speed

Explore more on our [Pricing Page](https://www.coinapi.io/products/market-data-api/pricing) or reach out to our support team for personalized guidance.

### 43. How is L2 Order Book data aggregated across exchanges, particularly when combining centralized and decentralized sources?[​](/general/faq/Market-Data-API/#43-how-is-l2-order-book-data-aggregated-across-exchanges-particularly-when-combining-centralized-and-decentralized-sources "Direct link to 43. How is L2 Order Book data aggregated across exchanges, particularly when combining centralized and decentralized sources?")

CoinAPI provides raw Level 2 (L2) Order Book data on a per-symbol and per-exchange basis. This means:

* There is no aggregation across exchanges.
* Centralized and decentralized exchange data are kept separate.
* Each Order Book reflects the state of a single trading pair on a single exchange (e.g., `BINANCE_SPOT_BTC_USDT` or `UNISWAP-V3-ETHEREUM_SPOT_ETH_USDT`).

If you need aggregated Order Book views, you’ll need to implement that logic client-side by combining multiple Order Books using your preferred methodology.

For further details, visit the [Order Book endpoint documentation](https://docs.coinapi.io/market-data/rest-api/order-book/).

### 44. How are price levels with different tick sizes reconciled?[​](/general/faq/Market-Data-API/#44-how-are-price-levels-with-different-tick-sizes-reconciled "Direct link to 44. How are price levels with different tick sizes reconciled?")

CoinAPI delivers raw, unaggregated Order Book data as provided by each individual exchange. Since we do not aggregate Order Book data across exchanges, we also do not reconcile differences in tick sizes between trading venues.

Tick sizes can vary significantly between exchanges and trading pairs. If your application requires a harmonized view of price levels, including reconciling different tick sizes, this logic must be implemented on your side as part of a custom aggregation strategy.

We believe that aggregated Order Books are generally not meaningful in the crypto space due to varying market structures, liquidity depth, and tick sizes.

For technical guidance, you can explore our [Order Book API documentation](https://docs.coinapi.io/market-data/rest-api/order-book/).

### 45. Are synthetic DEX order books (e.g., Uniswap pools) combined with CEX data in the same aggregate feed?[​](/general/faq/Market-Data-API/#45-are-synthetic-dex-order-books-eg-uniswap-pools-combined-with-cex-data-in-the-same-aggregate-feed "Direct link to 45. Are synthetic DEX order books (e.g., Uniswap pools) combined with CEX data in the same aggregate feed?")

No, CoinAPI does not currently offer aggregated Order Book data across exchanges, including combinations of centralized exchanges (CEXs) and decentralized exchanges (DEXs).

Each order book is venue-specific, meaning that synthetic liquidity sources like Uniswap or Curve are maintained separately from centralized exchanges. This ensures accuracy and preserves the unique structure of each exchange’s market data.

If you require an aggregated view that includes both CEX and DEX data, you’ll need to implement that logic on your side using the raw data we provide.

You can explore detailed Order Book structures in our [Order Book API documentation](https://docs.coinapi.io/market-data/rest-api/order-book/).

### 46. If synthetic DEX and CEX order books were combined, how is the depth normalized or bucketed to make them comparable?[​](/general/faq/Market-Data-API/#46-if-synthetic-dex-and-cex-order-books-were-combined-how-is-the-depth-normalized-or-bucketed-to-make-them-comparable "Direct link to 46. If synthetic DEX and CEX order books were combined, how is the depth normalized or bucketed to make them comparable?")

This does not apply, as CoinAPI does not aggregate Order Book data across exchanges, whether centralized or decentralized.

Order Book data is provided in its raw, venue-specific format, maintaining the original structure, price levels, and tick sizes of each source. Therefore, normalization or bucketing across different exchange types is not performed by CoinAPI.

If you require normalized depth across multiple venues, this would need to be handled on your end by processing and standardizing the raw data we supply. Learn more about our order book structure in the [Order Book API documentation](https://docs.coinapi.io/market-data/rest-api/order-book/).

### 47. Is there a reference list of the available aggregated symbol IDs (e.g., BTC\_USD, ETH\_USD)?[​](/general/faq/Market-Data-API/#47-is-there-a-reference-list-of-the-available-aggregated-symbol-ids-eg-btc_usd-eth_usd "Direct link to 47. Is there a reference list of the available aggregated symbol IDs (e.g., BTC_USD, ETH_USD)?")

Yes, CoinAPI provides a comprehensive mapping of exchange-specific identifiers to our standardized symbol IDs and asset IDs through the following endpoints:

* `/v1/symbols`: Retrieves all available symbols, including their exchange, instrument type, and asset identifiers.
* `/v1/assets`: Returns a list of all standardized asset IDs used across our platform.

These endpoints allow you to find and reference the aggregated symbol IDs used for data queries (such as `BTC_USD`, `ETH_USD`, etc.) across supported venues. You can also filter by exchange or asset to narrow your search.

### 48. How can I estimate liquidity and slippage across exchanges — especially when quote currencies differ (e.g., BTC/USDC vs BTC/USDT)?[​](/general/faq/Market-Data-API/#48-how-can-i-estimate-liquidity-and-slippage-across-exchanges--especially-when-quote-currencies-differ-eg-btcusdc-vs-btcusdt "Direct link to 48. How can I estimate liquidity and slippage across exchanges — especially when quote currencies differ (e.g., BTC/USDC vs BTC/USDT)?")

Estimating liquidity and slippage across exchanges and quote currencies is a complex challenge due to discrepancies in quote asset pricing (like USDC vs. USDT). CoinAPI does not aggregate order book liquidity across exchanges or normalize it into a unified feed like `BTC_USD`.

At this time:

* There is no built-in aggregation of liquidity data across centralized and decentralized exchanges.
* Normalization across quote currencies and liquidity bucketing must be handled on your side, depending on your analysis methodology.
* CoinAPI provides raw Quotes and Order Book data (both via REST API and Flat Files), which include precise snapshots and updates per symbol per exchange.

If you're looking to analyze liquidity over time or estimate slippage, you'll need to implement your own data normalization logic and aggregation based on the raw market data we provide.

### 49. Which exchanges support L3 (Full Depth Order Book) data?[​](/general/faq/Market-Data-API/#49-which-exchanges-support-l3-full-depth-order-book-data "Direct link to 49. Which exchanges support L3 (Full Depth Order Book) data?")

CoinAPI currently provides L3 Order Book data (also known as Full Depth Order Book or Level 3 data) for the following exchanges:

* BITSO
* COINBASE

This data includes the most granular view of the order book, allowing access to individual order placements, modifications, and deletions. For technical details on this data type, refer to the [Flat Files Limit Book Documentation](https://docs.coinapi.io/flat-files-api/data-types/limitbook) or [WebSocket L3 Order Book](https://docs.coinapi.io/market-data/websocket/messages#orderbook-l3-full--in).

### 50. I can’t find the perpetual (PERP) symbols for my exchange. Where are they?[​](/general/faq/Market-Data-API/#50-i-cant-find-the-perpetual-perp-symbols-for-my-exchange-where-are-they "Direct link to 50. I can’t find the perpetual (PERP) symbols for my exchange. Where are they?")

In some cases, **SPOT and PERP symbols are listed under separate exchange IDs**, even if they belong to the same exchange. This distinction is made because the exchange itself exposes SPOT and PERP markets through **separate APIs**, and we reflect that structure in our own system.

Example: Exchanges with separated PERP symbols

* `BINANCEFTS` – Binance USD-M Futures (USDT/fapi)
* `BINANCEFTSC` – Binance COIN-M Futures (Coin/dapi)
* `KRAKENFTS` – Kraken Futures
* `BITGETFTS` – Bitget Futures

Example: Exchanges with unified symbol listings

* `OKEX`
* `DERIBIT`

To retrieve PERP symbols, make sure you're querying the appropriate exchange ID using the `/v1/symbols` endpoint with a `filter_exchange_id` parameter.

### 51. Can I use your data to analyze true market trades involving limit orders?[​](/general/faq/Market-Data-API/#51-can-i-use-your-data-to-analyze-true-market-trades-involving-limit-orders "Direct link to 51. Can I use your data to analyze true market trades involving limit orders?")

Yes! You can gain valuable insight into market trades and limit orders by leveraging two key data types:

* Trades Endpoint:

This provides details on executed transactions, which includes price, volume, and timestamp. These are actual trades that occurred between market participants. Use this to analyze trade flow and execution.

* Order Book Endpoint (L2/L3):

This gives you a passive view of the market — specifically, all the outstanding limit orders on both the bid and ask sides. It helps you understand market depth, liquidity, and the context in which trades occur.

### 52. How do I read the Usage Metrics Dashboard and understand the difference between Tier 1 and Tier 2 data?[​](/general/faq/Market-Data-API/#52-how-do-i-read-the-usage-metrics-dashboard-and-understand-the-difference-between-tier-1-and-tier-2-data "Direct link to 52. How do I read the Usage Metrics Dashboard and understand the difference between Tier 1 and Tier 2 data?")

The Usage Metrics Dashboard provides insights into how much data and how many credits you're consuming across CoinAPI products. Here’s a breakdown of how to interpret it: Understanding the Tiers:

Tier 1 Data

Represents the amount of high-volume market data (like trades, quotes, and order book data) transferred via the WebSocket API. This is typically used for real-time trading applications and market monitoring.

Tier 2 Data

Refers to low-volume data such as metadata, OHLCV (candlestick data), and exchange rates delivered via the WebSocket API.

How to Activate Tier 1 or Tier 2:

No manual activation is needed. Tiers are automatically enabled based on your subscription plan. For example, if you're on the Professional Plan, your daily quota includes:

100,000 REST Credits

512 GB of Tier 1 WebSocket Data

64 GB of Tier 2 WebSocket Data

FIX API access

### 52. How do I filter symbols in my subscription?[​](/general/faq/Market-Data-API/#52-how-do-i-filter-symbols-in-my-subscription "Direct link to 52. How do I filter symbols in my subscription?")

To filter symbols when subscribing via WebSocket, use the `subscribe_filter_symbol_id` parameter. Here's how it works:

* Prefix Match (Default):

  The parameter filters symbols that start with the listed value(s).

  For example, `"subscribe_filter_symbol_id": ["BINANCE_SPOT_BTC_"]` will match all symbols starting with that prefix, such as `BINANCE_SPOT_BTC_USDT`.
* Exact Match:

  If you append a character to the end of a symbol ID, the system performs an exact match instead of a prefix match.

  For example, `"subscribe_filter_symbol_id": ["BINANCE_SPOT_BTC_USDT$"]` will match only that exact symbol.

### 53. Can I test the LMAX add-on for a few days?[​](/general/faq/Market-Data-API/#53-can-i-test-the-lmax-add-on-for-a-few-days "Direct link to 53. Can I test the LMAX add-on for a few days?")

The LMAX Digital Exchange provides highly granular, institutional-grade market data. Due to our contractual agreement with LMAX, we are strictly prohibited from offering this data:

* In any free trial capacity
* As sample datasets
* In any aggregated or altered format outside of the full subscription

This level of data quality is a key differentiator for our offering, but it also comes with firm legal restrictions from the exchange itself.

Unfortunately, we are unable to provide test access, even on a limited basis. If you require further details about what’s included in the LMAX add-on or wish to explore alternative data options, our team would be happy to assist.

### 54. How do I connect to the FIX API — via gateway or data feed?[​](/general/faq/Market-Data-API/#54-how-do-i-connect-to-the-fix-api--via-gateway-or-data-feed "Direct link to 54. How do I connect to the FIX API — via gateway or data feed?")

You connect to the FIX API by establishing a standard FIX session directly with the CoinAPI FIX gateway. This involves configuring your FIX client (initiator) to connect to our designated FIX endpoints. Example endpoint:

🔗 `fix.coinapi.io:3303`

You can also choose a region-specific endpoint depending on your setup. Full endpoint documentation is available here:

[📄 FIX API Endpoints](https://docs.coinapi.io/market-data/fix/#endpoints)

Key Details:

* The FIX API provides real-time market data streaming.
* It does not support historical data retrieval. For historical data, you’ll need to use our REST API instead:

  [📄 REST API Overview](https://docs.coinapi.io/market-data/#overview-of-the-apis)
* For real-time data streaming as an alternative to FIX, you can also use our [WebSocket API](https://docs.coinapi.io/market-data/websocket/).

If you're looking for ultra-low latency and institutional-grade market access, FIX is ideal. For flexibility or developer-friendly streaming, WebSocket may suit your use case better.

### 55. Does the Startup plan include buy/sell volume and percentage data?[​](/general/faq/Market-Data-API/#55-does-the-startup-plan-include-buysell-volume-and-percentage-data "Direct link to 55. Does the Startup plan include buy/sell volume and percentage data?")

We understand you're looking for metrics such as buy volume, sell volume, and buy/sell percentages. Currently, CoinAPI does not provide this data as pre-aggregated metrics via any endpoint — including under the Startup plan.

However, we do offer comprehensive raw data (Trades, Quotes, Order Book) that enables you to calculate these values independently within your own systems.

You can explore the available data types and endpoints here:

[📄 Market Data API Documentation](https://docs.coinapi.io/market-data/)

If you're interested in building this logic internally or need guidance on calculating such metrics from raw data, feel free to reach out to our support team.

### 56. How do I calculate REST credit usage for the `/v1/orderbooks/:symbol_id/history` endpoint?[​](/general/faq/Market-Data-API/#56-how-do-i-calculate-rest-credit-usage-for-the-v1orderbookssymbol_idhistory-endpoint "Direct link to 56-how-do-i-calculate-rest-credit-usage-for-the-v1orderbookssymbol_idhistory-endpoint")

REST credit usage depends on the amount of data requested, not just the number of times you call the API. Here’s how it works:

General Credit Rules:

* If no `limit` parameter is used, 1 API call = 1 REST credit (up to the default limit of 100 records).
* If a `limit` parameter is used, every 100 data points = 1 REST credit.
* Using the `date` parameter overrides the limit and returns all data for the day, costing 10 credits max (assuming >1000 records).

Example Scenarios:

1. Without `limit` parameter:

```
plaintext  
https://rest.coinapi.io/v1/orderbooks/BINANCE_SPOT_BTC_USDT/history?time_start=2025-05-01T00:00:00&time_end=2025-05-01T10:00:00
```

Usage: 1 REST credit (default limit applies).

1. With `limit=200`:

```
plaintext  
https://rest.coinapi.io/v1/orderbooks/BINANCE_SPOT_BTC_USDT/history?time_start=2025-05-01T00:00:00&time_end=2025-05-01T10:00:00&limit=200
```

Usage: 2 REST credits.

1. Using the `date` parameter:

```
plaintext  
KopiujEdytuj  
https://rest.coinapi.io/v1/orderbooks/BINANCE_SPOT_BTC_USDT/history?date=2025-05-01
```

Usage: Up to 10 REST credits for full-day data.

For the Startup Plan:

* You receive 1,000 REST credits/day.
* If each daily request consumes 10 credits, you could retrieve data for 100 days per day.
* Keep in mind: other endpoints like Metadata also consume credits and may reduce your daily allowance.

More info: [API Limits and Billing Metrics](https://docs.coinapi.io/market-data/api-limits-and-billing-metrics)

For precise control, always monitor usage via the Customer Portal.

### 57. Why are some trades received via WebSocket showing zero volume? Should they affect OHLC calculations?[​](/general/faq/Market-Data-API/#57-why-are-some-trades-received-via-websocket-showing-zero-volume-should-they-affect-ohlc-calculations "Direct link to 57. Why are some trades received via WebSocket showing zero volume? Should they affect OHLC calculations?")

Yes, occasionally you may observe trades in the WebSocket stream that have a `size: 0`. These are not actual executed trades but rather markers—commonly used to indicate data points such as index ticks or indicative prices.

Key Points:

* A `size: 0` trade does not represent a real volume exchange.
* These trades should not influence OHLCV calculations (open, high, low, close, volume).
* They are intended to mark price points, often for indexing purposes or internal synchronization.

Documentation Reference: [Message Variables — CoinAPI WebSocket](https://docs.coinapi.io/market-data/websocket/messages#message-variables)

If you are generating candlestick charts or volume-based analytics, we recommend filtering out these entries to maintain data accuracy.

### 58. Why am I seeing trades with zero size in non-index symbols like BITRUE\_SPOT\_XAUT\_USDT?[​](/general/faq/Market-Data-API/#58-why-am-i-seeing-trades-with-zero-size-in-non-index-symbols-like-bitrue_spot_xaut_usdt "Direct link to 58. Why am I seeing trades with zero size in non-index symbols like BITRUE_SPOT_XAUT_USDT?")

Trades with `size: 0` in CoinAPI’s data—regardless of whether they pertain to an index or a standard trading pair like `BITRUE_SPOT_XAUT_USDT`—do not represent actual asset exchanges. These are non-transactional markers used for internal data signaling.

What do size: 0 trades mean?

* They act as reference points or flags within the data stream.
* They may be used for:
  + Maintaining stream synchronization
  + Keep-alive events
  + Signaling the end of a trading batch
  + Miscellaneous event tagging (e.g., market open/close, reset)

Important: These entries should be excluded from your trade analysis, volume aggregation, and OHLCV candle generation.

If you’re unsure how to programmatically filter them, feel free to contact our support team for sample logic or SDK guidance.

### 59. If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?[​](/general/faq/Market-Data-API/#59-if-i-wanted-to-just-buy-a-bulk-download-for-lets-say-aergo-usd-from-the-coinbase-exchange-for-the-order-book-data-is-that-possible-or-do-i-have-to-just-loop-through-the-api-to-get-all-the-data "Direct link to 59. If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?")

Yes, you can purchase daily full-limit order book data for specific trading pairs such as AERGO-USD from the Coinbase exchange via our Flat Files product. This allows you to download bulk historical data without having to loop through API calls.

Alternatively, if you prefer using the Market Data API, you can access historical order book data using the `date` parameter. However, please note:

* If you're looking to retrieve data over a range of dates, each day must be requested individually—this applies to both API calls and Flat Files downloads.
* For API access, using the `date` parameter ensures the complete dataset for that specific day is retrieved.

For larger date ranges or bulk needs, Flat Files offer a more efficient and cost-effective approach.

### 60. Do you support real-time streaming via WebSocket for trades, quotes and L2 Order Book / Depth?[​](/general/faq/Market-Data-API/#60-do-you-support-real-time-streaming-via-websocket-for-trades-quotes-and-l2-order-book--depth "Direct link to 60. Do you support real-time streaming via WebSocket for trades, quotes and L2 Order Book / Depth?")

Yes, we support real-time streaming via WebSocket for all the mentioned data types:

* Trades – Stream live executed transactions for selected symbols.
* Quotes – Get real-time updates for best bid and ask prices.
* L2 Order Book (Depth) – Access full market depth updates with live order book snapshots and changes.

For a complete list of supported data types and more technical details, please refer to our [WebSocket API documentation](https://docs.coinapi.io/market-data/websocket/general#data-types).

Let us know if you need help setting up your WebSocket feed or managing subscriptions.

### 61. Do you offer data for BTC/USDT and ETH/USDT pairs, and support futures market data?[​](/general/faq/Market-Data-API/#61-do-you-offer-data-for-btcusdt-and-ethusdt-pairs-and-support-futures-market-data "Direct link to 61. Do you offer data for BTC/USDT and ETH/USDT pairs, and support futures market data?")

Yes, we provide data for BTC/USDT and ETH/USDT trading pairs—as long as they are active and available on the exchanges we support. These pairs are covered extensively in our Market Data API across spot, futures, and options markets.

We also support futures market data for a wide range of symbols. You can explore all the available futures symbols and supported exchanges through our Metadata Tables, which offer downloadable datasets for comprehensive review:

[Metadata Tables - Supported Exchanges and Symbols](https://docs.coinapi.io/market-data/metadata-tables/introduction)

These tables will help you identify all supported trading venues and the available instrument types (including PERP, FUTURES, and OPTIONS), ensuring you get exactly the data you need.

For more insights into how we serve institutional-grade data coverage—including for exotic and futures pairs—check out how Wyden scaled their operations using CoinAPI’s infrastructure.

### 62. What are the current rate limits and latency expectations for WebSocket streaming and REST polling endpoints?[​](/general/faq/Market-Data-API/#62-what-are-the-current-rate-limits-and-latency-expectations-for-websocket-streaming-and-rest-polling-endpoints "Direct link to 62. What are the current rate limits and latency expectations for WebSocket streaming and REST polling endpoints?")

**WebSocket Streaming**

* Rate Limit:

  WebSocket connections are limited to 10 `hello` messages per 10 seconds. To maximize efficiency and performance, we recommend consolidating all your required subscriptions into a single `hello` message whenever possible.
* Latency:

  WebSocket is optimized for real-time data delivery, offering significantly lower latency than REST. However, actual latency depends on several factors including:

  + Your physical location
  + Network provider and quality
  + Exchange location and responsiveness

  For example, achieving latency below 100ms between London and Binance may require specialized routing or proximity hosting. The default latency from London to Binance can be around 250ms.

  🔧 For mission-critical low-latency setups, our Enterprise Plan offers:

  + Dedicated infrastructure
  + Custom routing configurations
  + Latency Service-Level Agreements (SLAs)

    [Learn more about reducing API latency](https://docs.coinapi.io/market-data/latency-faq/how-to-reduce-market-data-apis-latency)

**REST API Polling**

* Rate Limits:

  We strive to accept as many requests as possible, scaling infrastructure dynamically. However, some endpoints might return a `429 Too Many Requests` error depending on:

  + The nature of the endpoint
  + Backend load distribution
  + API protocol behavior

  [Full throttling documentation](https://docs.coinapi.io/general/throttling)
* Latency:

  REST API latency varies more widely than WebSocket. While we aim to minimize delays, response times can be influenced by server load, your query volume, and external factors like your internet connectivity and geographic proximity to our datacenters.
* Credit Usage:

  A daily credit quota applies based on your subscription tier. Each request consumes credits based on the data volume and endpoint accessed.

For best practices, REST is ideal for on-demand snapshots or historical queries, while WebSocket is recommended for continuous real-time streaming.

### 63. Why do some order books have crossed prices (bid ≥ ask)?[​](/general/faq/Market-Data-API/#63-why-do-some-order-books-have-crossed-prices-bid--ask "Direct link to 63. Why do some order books have crossed prices (bid ≥ ask)?")

Crossed order books can occur when exchanges match trades in batches (e.g., every 100ms) or accept orders under high load before matching them. CoinAPI delivers raw data as received, which may include such cases.

### 64. Why is CoinAPI’s OHLCV data different from the exchange chart?[​](/general/faq/Market-Data-API/#64-why-is-coinapis-ohlcv-data-different-from-the-exchange-chart "Direct link to 64. Why is CoinAPI’s OHLCV data different from the exchange chart?")

Exchanges use different methods to aggregate OHLCV candles, which may include delayed, averaged, or custom logic. CoinAPI standardizes OHLCV aggregation across all exchanges using a unified method based on real-time trade streams and reception timestamps. This ensures consistency, but values may differ slightly from the exchange’s native chart.

### 65. How can I view a list of symbols by exchange, market type, or asset in CoinAPI?[​](/general/faq/Market-Data-API/#65-how-can-i-view-a-list-of-symbols-by-exchange-market-type-or-asset-in-coinapi "Direct link to 65. How can I view a list of symbols by exchange, market type, or asset in CoinAPI?")

You can use the `/v1/symbols` endpoint to filter trading symbols by exchange, market type, or specific crypto assets. The API supports multiple query parameters:

Examples:

* Symbols for Coinbase exchange:

  `https://rest.coinapi.io/v1/symbols?filter_exchange_id=COINBASE`
* Symbols for Chainlink (LINK):

  `https://rest.coinapi.io/v1/symbols?filter_asset_id=LINK`
* Binance Spot market only:

  `https://rest.coinapi.io/v1/symbols?filter_symbol_id=BINANCE_SPOT_`
* Binance Spot BTC base markets:

  `https://rest.coinapi.io/v1/symbols?filter_symbol_id=BINANCE_SPOT_BTC_`
* ETH/BTC pairs across all exchanges:

  `https://rest.coinapi.io/v1/symbols?filter_symbol_id=_ETH_BTC`
* Spot market pairs like XRP/USD:

  `https://rest.coinapi.io/v1/symbols?filter_symbol_id=_SPOT_XRP_USD`

For symbol formatting and ID patterns, refer to:

* [Symbol Identifier Guide](https://docs.coinapi.io/market-data/rest-api/metadata#symbol-identifier)
* [List All Symbols Endpoint](https://docs.coinapi.io/market-data/rest-api/metadata#list-all-symbols-get)

### 66. What does a WebSocket reconnect message mean, and how should I handle it?[​](/general/faq/Market-Data-API/#66-what-does-a-websocket-reconnect-message-mean-and-how-should-i-handle-it "Direct link to 66. What does a WebSocket reconnect message mean, and how should I handle it?")

A reconnect message is sent by CoinAPI’s WebSocket server when the server is scheduled for a restart or shutdown. It contains a precise timestamp indicating when the connection will be closed.

📨 Example reconnect message:

```
json  
{  
  "type": "reconnect",  
  "within_seconds": 10,  
  "before_time": "2020-08-06T19:19:09.7035429Z"  
}
```

How to handle reconnects:

Choose one of the following strategies based on your application's requirements:

1. Wait and reconnect

   Allow the current connection to close, then establish a new one.
2. Reconnect immediately

   Terminate the current session and initiate a new WebSocket connection right away.
3. Dual connection switch (advanced)

   Open a second connection and resubscribe to the same data scope. Once the original connection closes, seamlessly switch to the new one—ensuring continuity in data streams.

   *Note: This approach is ideal for systems that rely on snapshot + update message sequencing.*

For robust applications, implementing a seamless reconnection logic ensures minimal downtime and uninterrupted data processing.

### 67. What are the risks of using multiple concurrent WebSocket connections with the same API key?[​](/general/faq/Market-Data-API/#67-what-are-the-risks-of-using-multiple-concurrent-websocket-connections-with-the-same-api-key "Direct link to 67. What are the risks of using multiple concurrent WebSocket connections with the same API key?")

Running multiple WebSocket connections concurrently—especially with shared credentials—introduces the following risks:

* Key misuse or leakage across environments (e.g., dev/test/prod)
* Triggering hard concurrency limits, which may result in dropped connections or access blocks
* Security vulnerabilities if API keys are not properly isolated

Subscriptions typically allow only one concurrent WebSocket session. For advanced use cases (e.g., multi-region apps), contact our team to discuss upgrading your plan.

### 68. Why do some CoinAPI symbol IDs have an extra prefix or suffix?[​](/general/faq/Market-Data-API/#68-why-do-some-coinapi-symbol-ids-have-an-extra-prefix-or-suffix "Direct link to 68. Why do some CoinAPI symbol IDs have an extra prefix or suffix?")

In rare cases where multiple markets result in the same `symbol_id`, CoinAPI appends an additional identifier—prefixed with an underscore (`_`)—to ensure uniqueness.

This occurs when:

* Exchanges list duplicate or deprecated markets
* API changes lead to symbol re-registration
* Multiple market feeds represent the same trading pair under different APIs

Example:

* Original: `OKEX_FTS_ETH_USD_190927`
* Duplicate-resolved: `OKEX_FTS_ETH_USD_190927_5656B6`

This additional suffix helps distinguish markets and ensures accurate symbol mapping in your integration.

Full explanation and symbol schema available here:

[List All Symbols – API Docs](https://docs.coinapi.io/#list-all-symbols-get)

### 69. How granular is CoinAPI’s data?[​](/general/faq/Market-Data-API/#69-how-granular-is-coinapis-data "Direct link to 69. How granular is CoinAPI’s data?")

CoinAPI provides both aggregated and raw data types, depending on the endpoint or product you are using.

* Aggregated data types include:

  + OHLCV (Open, High, Low, Close, Volume)
  + Exchange Rates

  These are aggregated over fixed time intervals. The smallest supported aggregation period is 1 second.
* Raw data types include:

  + Trades
  + Quotes
  + Order Book

  These are provided in real-time, with every individual market event captured and made available through both real-time streams and historical API access.

### 70. How is trade volume calculated in CoinAPI?[​](/general/faq/Market-Data-API/#70-how-is-trade-volume-calculated-in-coinapi "Direct link to 70. How is trade volume calculated in CoinAPI?")

Trade volume in CoinAPI is calculated directly from raw trade data collected via APIs provided by each exchange. We do not rely on pre-aggregated volume figures published by the exchanges themselves.

Instead:

* Every individual trade is recorded with its quantity and price
* Aggregation (e.g., for OHLCV or volume summaries) is done internally based on this raw data
* This ensures consistency across sources and high accuracy

This method guarantees that volume metrics are built from the ground up using actual trade events, providing a reliable and transparent foundation for analysis.

### 71. How can I avoid losing messages or experiencing delays when using CoinAPI’s WebSocket stream?[​](/general/faq/Market-Data-API/#71-how-can-i-avoid-losing-messages-or-experiencing-delays-when-using-coinapis-websocket-stream "Direct link to 71. How can I avoid losing messages or experiencing delays when using CoinAPI’s WebSocket stream?")

Lost messages or delays on the WebSocket stream typically occur when your client cannot keep up with the volume of incoming data. You can detect message loss by observing gaps in the sequence number field on incoming messages.

Common causes include:

1. Bandwidth limitations or network bottlenecks
2. Lack of separation between message receiving and parsing/processing threads
3. No CPU affinity set for the thread handling incoming messages
4. CPU resource bottlenecks on the receiving thread
5. Infrequent polling of the TCP socket buffer
6. Per-message heap allocation causing garbage collection pressure

If your client falls behind, here’s what happens:

1. Your system's TCP window closes, signaling you can’t receive more data
2. CoinAPI's TCP stack starts queuing outbound messages
3. A temporary internal buffer is created to retry message delivery (introducing delay)
4. If the client still can’t catch up, CoinAPI will begin dropping messages

How to mitigate:

* Use dedicated threads for reading from the socket
* Avoid unnecessary object creation during message handling
* Ensure consistent and fast parsing to keep up with data flow
* Monitor CPU and memory performance, and scale resources if needed
* Review system tuning techniques related to TCP flow control

More general background can be found by researching: *TCP Flow Control*

### 72. Is latency higher for exchanges that provide only REST APIs?[​](/general/faq/Market-Data-API/#72-is-latency-higher-for-exchanges-that-provide-only-rest-apis "Direct link to 72. Is latency higher for exchanges that provide only REST APIs?")

Yes, latency is typically higher for exchanges that offer only REST API access compared to those that support WebSocket feeds.

REST APIs generally introduce more delay because:

* They require polling instead of streaming
* They are subject to stricter rate limits and slower response cycles
* The exchange may throttle data frequency

To minimize latency from these exchanges, CoinAPI uses **hundreds of dedicated servers** to parallelize requests and bypass REST-specific limitations. This allows us to collect data as fast as technically possible given the constraints of each exchange.

### 73. How can I query OHLCV data filtered by specific coins and exchanges using the REST API?[​](/general/faq/Market-Data-API/#73-how-can-i-query-ohlcv-data-filtered-by-specific-coins-and-exchanges-using-the-rest-api "Direct link to 73. How can I query OHLCV data filtered by specific coins and exchanges using the REST API?")

When using the REST API to access OHLCV data, each request must target a specific symbol (e.g., `BINANCE_SPOT_BTC_USDT`). There is currently no bulk query option for filtering OHLCV data across multiple symbols or exchanges in a single API request.

For example:

* To get 1-minute candles for multiple coins on a specific exchange, you must loop over each symbol individually
* This applies regardless of whether you're filtering by asset or exchange

### 74. Why does the REST API return an empty array for OHLCV data instead of a 550 error?[​](/general/faq/Market-Data-API/#74-why-does-the-rest-api-return-an-empty-array-for-ohlcv-data-instead-of-a-550-error "Direct link to 74. Why does the REST API return an empty array for OHLCV data instead of a 550 error?")

When using the REST API to request OHLCV data, the response is structured as a collection (e.g., JSON array). If no data is available within the specified time range, the response will be an empty array rather than an error.

This behavior is by design and reflects a valid response where:

* The requested time range exists
* The response structure is intact
* No trade activity occurred during the period (resulting in no OHLCV values)

In contrast, an HTTP 550 error is returned when requesting a specific object—such as a current exchange rate (e.g., BTC/USD)—and the requested value does not exist. Since a singular object is expected in that case, the lack of data results in a failed request.

Special note on OHLCV with no trades:

If there are no trades in a given period, no OHLCV record will be generated because open, high, low, and close values are undefined.

However, you can use the `include_empty_items=true` parameter to return time periods with no trade activity. In such cases, only the `time_period_start` and `time_period_end` will be present in the response.

Relevant documentation:

* [OHLCV endpoint details](https://docs.coinapi.io/market-data/rest-api/ohlcv)
* [CoinAPI REST API request/response handling](https://docs.coinapi.io/market-data/rest-api#http-requests)

### 75. What are the benefits of using the CoinAPI WebSocket SDK?[​](/general/faq/Market-Data-API/#75-what-are-the-benefits-of-using-the-coinapi-websocket-sdk "Direct link to 75. What are the benefits of using the CoinAPI WebSocket SDK?")

CoinAPI’s WebSocket SDK offers a production-ready implementation of the WebSocket client protocol, designed to reduce your development time and increase performance and reliability.

Key benefits:

* No need to implement or maintain the protocol

  The SDK handles all protocol-level logic so you can focus on your business logic.
* Fully tested implementation

  The WebSocket protocol is 100% covered with unit tests to ensure long-term stability.
* Built-in reliability features

  Automatic reconnection, heartbeat monitoring, and error handling are embedded and can be optionally logged via event hooks.
* Zero-allocation JSON parsing

  Designed for minimal CPU usage by avoiding unnecessary memory allocations.
* Optimized message processing

  Incoming messages are queued and handled by a separate thread to prevent TCP backpressure and ensure smooth performance under high load.
* Best practices included

  The SDK follows all recommended standards for high-throughput, low-latency WebSocket communication.

Using the SDK gives you a faster path to production with lower maintenance overhead and better runtime efficiency.

### 76. What data is delivered using CoinAPI’s local sites?[​](/general/faq/Market-Data-API/#76-what-data-is-delivered-using-coinapis-local-sites "Direct link to 76. What data is delivered using CoinAPI’s local sites?")

All real-time data is delivered through CoinAPI’s geographically distributed local sites to minimize latency and optimize performance.

Real-time data includes:

* All `/current` endpoints in the REST API
* The `/trades/latest` endpoint in the REST API
* The `/ohlcv/latest` endpoint in the REST API
* All streams from the WebSocket API
* All sessions using the FIX API

These endpoints are latency-sensitive and therefore routed through the nearest available site using GeoDNS, ensuring faster response times and more stable connectivity.

### 77. What market symbol types are supported by CoinAPI?[​](/general/faq/Market-Data-API/#77-what-market-symbol-types-are-supported-by-coinapi "Direct link to 77. What market symbol types are supported by CoinAPI?")

CoinAPI supports a wide range of financial instruments across multiple cryptocurrency markets. Each symbol type corresponds to a distinct class of market data and is structured using a consistent identifier format.

Supported Symbol Types

| Type | Name | Description |
| --- | --- | --- |
| SPOT | FX Spot | Agreement to exchange one asset for another (e.g., buy BTC for USD) |
| FUTURES | Futures contract | A derivative contract to trade FX Spot at a future date and predetermined price |
| OPTION | Option contract | A contract to buy/sell FX Spot at a specific price on a future date, optionally exercised |
| PERPETUAL | Perpetual contract | Derivative that continuously tracks spot price with no fixed delivery date |
| INDEX | Index | Statistical indicator composed from other instruments (e.g., BTC/USD index) |
| CREDIT | Credit/Funding | Lending/borrowing offers in margin markets; price indicates daily interest rate |
| CONTRACT | Contract | Includes spreads, swaps, or other complex financial instruments |

Symbol Identifier Patterns

| Type | Pattern |
| --- | --- |
| SPOT | `{`exchange\_id`}_SPOT_{`asset\_id\_base`}_{`asset\_id\_quote`}` |
| FUTURES | `{`exchange\_id`}_FTS_{`asset\_id\_base`}_{`asset\_id\_quote`}_{`YYMMDD`}` |
| OPTION | `{`exchange\_id`}*OPT*{`asset\_id\_base`}*{`asset\_id\_quote`}*{`YYMMDD`}*{`strike\_price`}*{`C |
| PERPETUAL | `{`exchange\_id`}_PERP_{`asset\_id\_base`}_{`asset\_id\_quote`}` |
| INDEX | `{`exchange\_id`}_IDX_{`index\_id`}` |
| CREDIT | `{`exchange\_id`}_CRE_{`asset\_id\_base`}` |
| CONTRACT | `{`exchange\_id`}_COT_{`contract\_id`}` |

Useful Resources

* List all symbols:

  <https://rest.coinapi.io/v1/symbols>
* Symbol identifier format reference:

  <https://docs.coinapi.io/market-data/rest-api/metadata#symbol-identifier>

### 78. What should I do if I encounter missing price data or data gaps?[​](/general/faq/Market-Data-API/#78-what-should-i-do-if-i-encounter-missing-price-data-or-data-gaps "Direct link to 78. What should I do if I encounter missing price data or data gaps?")

If you notice missing data or gaps in pricing, follow these steps:

1. Check Your API Key and Subscription
   * Ensure your API key is valid and has access to the data type you're requesting
   * Verify your subscription tier supports the asset class or protocol (e.g., tick data, OHLCV, order books)
2. Validate Your Request
   * Double-check the `symbol_id`, `time_start`, `time_end`, and `limit` parameters
   * Try querying a smaller time range or different exchange to isolate the issue
3. Use Metadata Endpoints
   * Use `/v1/symbols` and `/v1/assets` to confirm that the symbol exists and is currently supported
4. Contact Support
   * If the issue persists, submit a ticket at [support.coinapi.io](https://support.coinapi.io/hc/en-us/requests/new)
   * Include:
     + Affected `symbol_id(s)`
     + `time_start` and `time_end`
     + Your API key (if comfortable)
     + Sample response/output if applicable

Some short gaps may occur due to upstream exchange downtimes or API failures. For gap-resistant backfills, consider using Flat Files as a complement to API requests.

### 79. What is the typical latency of CoinAPI's REST Market Data API?[​](/general/faq/Market-Data-API/#79-what-is-the-typical-latency-of-coinapis-rest-market-data-api "Direct link to 79. What is the typical latency of CoinAPI's REST Market Data API?")

CoinAPI's REST Market Data API is optimized for low latency and high reliability, making it suitable for time-sensitive applications such as algorithmic trading and real-time analytics.

Key Performance Insights:

* Typical Latency: 100–200 milliseconds for small to medium-sized requests under normal network conditions
* Large Requests: May take longer, but initial response times (first-byte-out) remain consistently fast
* Global Infrastructure: CoinAPI operates hundreds of distributed servers worldwide to minimize latency and ensure optimal routing

Best Practices for Low-Latency Applications:

* Use parallel requests across multiple threads to reduce total wait time
* For ultra-low latency needs, consider switching to WebSocket or FIX API, which are designed for real-time data streaming
* Place servers geographically closer to CoinAPI’s endpoints or request AWS VPC peering (available under Enterprise plan)

Learn more in our [Performance Testing Guide](https://docs.coinapi.io/market-data/performance-testing-guide) or contact our support team for help with latency optimization.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Why does my WebSocket connection keep disconnecting with code 1006 and no reason?](/general/faq/API-Access-and-Integration/Why-does-my-WebSocket-connection-keep-disconnecting-with-code-1006-and-no-reason)[Next

EMS Trading API](/general/faq/EMS-Trading-API/)

* [Tips for Navigating This FAQ](/general/faq/Market-Data-API/#tips-for-navigating-this-faq)
* [Frequently Asked Questions](/general/faq/Market-Data-API/#frequently-asked-questions)
  + [1. Do crypto exchanges send duplicate trade data messages?](/general/faq/Market-Data-API/#1-do-crypto-exchanges-send-duplicate-trade-data-messages)
  + [2. Can historical order books reconstructed from L2 updates be crossed (bid-ask overlap) occasionally?](/general/faq/Market-Data-API/#2-can-historical-order-books-reconstructed-from-l2-updates-be-crossed-bid-ask-overlap-occasionally)
  + [3. Do you collect order books as snapshots or in streaming mode?](/general/faq/Market-Data-API/#3-do-you-collect-order-books-as-snapshots-or-in-streaming-mode)
  + [4. Do you offer historical crypto futures market data?](/general/faq/Market-Data-API/#4-do-you-offer-historical-crypto-futures-market-data)
  + [5. Do you provide historical options data?](/general/faq/Market-Data-API/#5-do-you-provide-historical-options-data)
  + [6. Do you provide market data in a normalized format?](/general/faq/Market-Data-API/#6-do-you-provide-market-data-in-a-normalized-format)
  + [7. Do you provide time-based Order Book aggregated data (e.g., OHLCV or interval-based snapshots)?](/general/faq/Market-Data-API/#7-do-you-provide-time-based-order-book-aggregated-data-eg-ohlcv-or-interval-based-snapshots)
  + [8. How are order book data snapshots provided?](/general/faq/Market-Data-API/#8-how-are-order-book-data-snapshots-provided)
  + [9. How does the full orderbook stream work?](/general/faq/Market-Data-API/#9-how-does-the-full-orderbook-stream-work)
  + [10. How historical raw market data is being sourced?](/general/faq/Market-Data-API/#10-how-historical-raw-market-data-is-being-sourced)
  + [11. How much historical data does CoinAPI have?](/general/faq/Market-Data-API/#11-how-much-historical-data-does-coinapi-have)
  + [12. How much historical data can I fetch from a single query?](/general/faq/Market-Data-API/#12-how-much-historical-data-can-i-fetch-from-a-single-query)
  + [13. What data types do you support?](/general/faq/Market-Data-API/#13-what-data-types-do-you-support)
  + [14. What does high frequency historical data mean?](/general/faq/Market-Data-API/#14-what-does-high-frequency-historical-data-mean)
  + [15. What is the difference between futures and perpetual swaps contracts?](/general/faq/Market-Data-API/#15-what-is-the-difference-between-futures-and-perpetual-swaps-contracts)
  + [16. What can L2 order book data be used for?](/general/faq/Market-Data-API/#16-what-can-l2-order-book-data-be-used-for)
  + [17. What can L3 order book data be used for?](/general/faq/Market-Data-API/#17-what-can-l3-order-book-data-be-used-for)
  + [18. What metrics does CoinAPI use to evaluate cryptocurrency exchange performance and activity?](/general/faq/Market-Data-API/#18-what-metrics-does-coinapi-use-to-evaluate-cryptocurrency-exchange-performance-and-activity)
  + [19. Why does the data source matter, and why does CoinAPI use real-time WebSocket feeds instead of relying on REST endpoints?](/general/faq/Market-Data-API/#19-why-does-the-data-source-matter-and-why-does-coinapi-use-real-time-websocket-feeds-instead-of-relying-on-rest-endpoints)
  + [20. Why is the `volume_1day_usd` value for BTC or ETH higher than on platforms like CoinGecko?](/general/faq/Market-Data-API/#20-why-is-the-volume_1day_usd-value-for-btc-or-eth-higher-than-on-platforms-like-coingecko)
  + [21. Why am I receiving multiple OHLCV updates for the same time window via WebSocket?](/general/faq/Market-Data-API/#21-why-am-i-receiving-multiple-ohlcv-updates-for-the-same-time-window-via-websocket)
  + [22. Can I retrieve time-aggregated order book data using `period_id` from the REST API?](/general/faq/Market-Data-API/#22-can-i-retrieve-time-aggregated-order-book-data-using-period_id-from-the-rest-api)
  + [23. Why is the `/v1/orderbooks/{`symbol\_id`}/history` endpoint slow for symbols like `BINANCE_SPOT_BTC_USDT`?](/general/faq/Market-Data-API/#23-why-is-the-v1orderbookssymbol_idhistory-endpoint-slow-for-symbols-like-binance_spot_btc_usdt)
  + [24. Does CoinAPI provide data for blockchain verification, deposit/withdrawal status, or token contract addresses?](/general/faq/Market-Data-API/#24-does-coinapi-provide-data-for-blockchain-verification-depositwithdrawal-status-or-token-contract-addresses)
  + [25. Does CoinAPI provide aggregated Kline, order book, trades, or market sentiment data across multiple exchanges?](/general/faq/Market-Data-API/#25-does-coinapi-provide-aggregated-kline-order-book-trades-or-market-sentiment-data-across-multiple-exchanges)
  + [26. Do you provide OHLC, turnover, trades, market cap for perpetuals, or funding rate data?](/general/faq/Market-Data-API/#26-do-you-provide-ohlc-turnover-trades-market-cap-for-perpetuals-or-funding-rate-data)
  + [27. Why am I only seeing SPOT symbols at `/v1/symbols`? How can I get PERP data?](/general/faq/Market-Data-API/#27-why-am-i-only-seeing-spot-symbols-at-v1symbols-how-can-i-get-perp-data)
  + [28. How much data would I use tracking real-time prices for 100 coins, updated 24 times per day?](/general/faq/Market-Data-API/#28-how-much-data-would-i-use-tracking-real-time-prices-for-100-coins-updated-24-times-per-day)
  + [29. Why does the `/v1/symbols` endpoint time out when I try to load all symbol metadata?](/general/faq/Market-Data-API/#29-why-does-the-v1symbols-endpoint-time-out-when-i-try-to-load-all-symbol-metadata)
  + [30. Do I need to send an unsubscribe message before closing a WebSocket connection?](/general/faq/Market-Data-API/#30-do-i-need-to-send-an-unsubscribe-message-before-closing-a-websocket-connection)
  + [31. Can I get historical ask, bid, and order book depth data from Binance, including snapshots and real-time updates from the past year?](/general/faq/Market-Data-API/#31-can-i-get-historical-ask-bid-and-order-book-depth-data-from-binance-including-snapshots-and-real-time-updates-from-the-past-year)
  + [32. How can I access historical bid/ask data and order book snapshots from Binance? Which CoinAPI product or plan should I choose?](/general/faq/Market-Data-API/#32-how-can-i-access-historical-bidask-data-and-order-book-snapshots-from-binance-which-coinapi-product-or-plan-should-i-choose)
  + [33. Can I retrieve aggregated liquidity data for mid-price ±X% over time intervals (e.g., 1h, 8h, 1d)?](/general/faq/Market-Data-API/#33-can-i-retrieve-aggregated-liquidity-data-for-mid-price-x-over-time-intervals-eg-1h-8h-1d)
  + [34. What is the unit of `volume_1day` in the `/v1/symbols` endpoint?](/general/faq/Market-Data-API/#34-what-is-the-unit-of-volume_1day-in-the-v1symbols-endpoint)
  + [35. Why am I receiving an empty response when fetching today’s historical order book data?](/general/faq/Market-Data-API/#35-why-am-i-receiving-an-empty-response-when-fetching-todays-historical-order-book-data)
  + [36. Why are the `X-RateLimit-Remaining` and `X-RateLimit-Reset` headers missing from the OHLCV Historical API responses?](/general/faq/Market-Data-API/#36-why-are-the-x-ratelimit-remaining-and-x-ratelimit-reset-headers-missing-from-the-ohlcv-historical-api-responses)
  + [37. How can I handle large result sets with the Historical OHLCV endpoint when the response doesn’t indicate total rows?](/general/faq/Market-Data-API/#37-how-can-i-handle-large-result-sets-with-the-historical-ohlcv-endpoint-when-the-response-doesnt-indicate-total-rows)
  + [38. Can I connect to the main WebSocket DS endpoint from multiple environments?](/general/faq/Market-Data-API/#38-can-i-connect-to-the-main-websocket-ds-endpoint-from-multiple-environments)
  + [39. How many credits are used by the OHLCV Exchanges endpoint?](/general/faq/Market-Data-API/#39-how-many-credits-are-used-by-the-ohlcv-exchanges-endpoint)
  + [40. Can I confirm that LMAX Digital data is available?](/general/faq/Market-Data-API/#40-can-i-confirm-that-lmax-digital-data-is-available)
  + [41. Is the datacenter located in London?](/general/faq/Market-Data-API/#41-is-the-datacenter-located-in-london)
  + [42. Is there any delay that occurs on your end?](/general/faq/Market-Data-API/#42-is-there-any-delay-that-occurs-on-your-end)
  + [43. How is L2 Order Book data aggregated across exchanges, particularly when combining centralized and decentralized sources?](/general/faq/Market-Data-API/#43-how-is-l2-order-book-data-aggregated-across-exchanges-particularly-when-combining-centralized-and-decentralized-sources)
  + [44. How are price levels with different tick sizes reconciled?](/general/faq/Market-Data-API/#44-how-are-price-levels-with-different-tick-sizes-reconciled)
  + [45. Are synthetic DEX order books (e.g., Uniswap pools) combined with CEX data in the same aggregate feed?](/general/faq/Market-Data-API/#45-are-synthetic-dex-order-books-eg-uniswap-pools-combined-with-cex-data-in-the-same-aggregate-feed)
  + [46. If synthetic DEX and CEX order books were combined, how is the depth normalized or bucketed to make them comparable?](/general/faq/Market-Data-API/#46-if-synthetic-dex-and-cex-order-books-were-combined-how-is-the-depth-normalized-or-bucketed-to-make-them-comparable)
  + [47. Is there a reference list of the available aggregated symbol IDs (e.g., BTC\_USD, ETH\_USD)?](/general/faq/Market-Data-API/#47-is-there-a-reference-list-of-the-available-aggregated-symbol-ids-eg-btc_usd-eth_usd)
  + [48. How can I estimate liquidity and slippage across exchanges — especially when quote currencies differ (e.g., BTC/USDC vs BTC/USDT)?](/general/faq/Market-Data-API/#48-how-can-i-estimate-liquidity-and-slippage-across-exchanges--especially-when-quote-currencies-differ-eg-btcusdc-vs-btcusdt)
  + [49. Which exchanges support L3 (Full Depth Order Book) data?](/general/faq/Market-Data-API/#49-which-exchanges-support-l3-full-depth-order-book-data)
  + [50. I can’t find the perpetual (PERP) symbols for my exchange. Where are they?](/general/faq/Market-Data-API/#50-i-cant-find-the-perpetual-perp-symbols-for-my-exchange-where-are-they)
  + [51. Can I use your data to analyze true market trades involving limit orders?](/general/faq/Market-Data-API/#51-can-i-use-your-data-to-analyze-true-market-trades-involving-limit-orders)
  + [52. How do I read the Usage Metrics Dashboard and understand the difference between Tier 1 and Tier 2 data?](/general/faq/Market-Data-API/#52-how-do-i-read-the-usage-metrics-dashboard-and-understand-the-difference-between-tier-1-and-tier-2-data)
  + [52. How do I filter symbols in my subscription?](/general/faq/Market-Data-API/#52-how-do-i-filter-symbols-in-my-subscription)
  + [53. Can I test the LMAX add-on for a few days?](/general/faq/Market-Data-API/#53-can-i-test-the-lmax-add-on-for-a-few-days)
  + [54. How do I connect to the FIX API — via gateway or data feed?](/general/faq/Market-Data-API/#54-how-do-i-connect-to-the-fix-api--via-gateway-or-data-feed)
  + [55. Does the Startup plan include buy/sell volume and percentage data?](/general/faq/Market-Data-API/#55-does-the-startup-plan-include-buysell-volume-and-percentage-data)
  + [56. How do I calculate REST credit usage for the `/v1/orderbooks/:symbol_id/history` endpoint?](/general/faq/Market-Data-API/#56-how-do-i-calculate-rest-credit-usage-for-the-v1orderbookssymbol_idhistory-endpoint)
  + [57. Why are some trades received via WebSocket showing zero volume? Should they affect OHLC calculations?](/general/faq/Market-Data-API/#57-why-are-some-trades-received-via-websocket-showing-zero-volume-should-they-affect-ohlc-calculations)
  + [58. Why am I seeing trades with zero size in non-index symbols like BITRUE\_SPOT\_XAUT\_USDT?](/general/faq/Market-Data-API/#58-why-am-i-seeing-trades-with-zero-size-in-non-index-symbols-like-bitrue_spot_xaut_usdt)
  + [59. If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?](/general/faq/Market-Data-API/#59-if-i-wanted-to-just-buy-a-bulk-download-for-lets-say-aergo-usd-from-the-coinbase-exchange-for-the-order-book-data-is-that-possible-or-do-i-have-to-just-loop-through-the-api-to-get-all-the-data)
  + [60. Do you support real-time streaming via WebSocket for trades, quotes and L2 Order Book / Depth?](/general/faq/Market-Data-API/#60-do-you-support-real-time-streaming-via-websocket-for-trades-quotes-and-l2-order-book--depth)
  + [61. Do you offer data for BTC/USDT and ETH/USDT pairs, and support futures market data?](/general/faq/Market-Data-API/#61-do-you-offer-data-for-btcusdt-and-ethusdt-pairs-and-support-futures-market-data)
  + [62. What are the current rate limits and latency expectations for WebSocket streaming and REST polling endpoints?](/general/faq/Market-Data-API/#62-what-are-the-current-rate-limits-and-latency-expectations-for-websocket-streaming-and-rest-polling-endpoints)
  + [63. Why do some order books have crossed prices (bid ≥ ask)?](/general/faq/Market-Data-API/#63-why-do-some-order-books-have-crossed-prices-bid--ask)
  + [64. Why is CoinAPI’s OHLCV data different from the exchange chart?](/general/faq/Market-Data-API/#64-why-is-coinapis-ohlcv-data-different-from-the-exchange-chart)
  + [65. How can I view a list of symbols by exchange, market type, or asset in CoinAPI?](/general/faq/Market-Data-API/#65-how-can-i-view-a-list-of-symbols-by-exchange-market-type-or-asset-in-coinapi)
  + [66. What does a WebSocket reconnect message mean, and how should I handle it?](/general/faq/Market-Data-API/#66-what-does-a-websocket-reconnect-message-mean-and-how-should-i-handle-it)
  + [67. What are the risks of using multiple concurrent WebSocket connections with the same API key?](/general/faq/Market-Data-API/#67-what-are-the-risks-of-using-multiple-concurrent-websocket-connections-with-the-same-api-key)
  + [68. Why do some CoinAPI symbol IDs have an extra prefix or suffix?](/general/faq/Market-Data-API/#68-why-do-some-coinapi-symbol-ids-have-an-extra-prefix-or-suffix)
  + [69. How granular is CoinAPI’s data?](/general/faq/Market-Data-API/#69-how-granular-is-coinapis-data)
  + [70. How is trade volume calculated in CoinAPI?](/general/faq/Market-Data-API/#70-how-is-trade-volume-calculated-in-coinapi)
  + [71. How can I avoid losing messages or experiencing delays when using CoinAPI’s WebSocket stream?](/general/faq/Market-Data-API/#71-how-can-i-avoid-losing-messages-or-experiencing-delays-when-using-coinapis-websocket-stream)
  + [72. Is latency higher for exchanges that provide only REST APIs?](/general/faq/Market-Data-API/#72-is-latency-higher-for-exchanges-that-provide-only-rest-apis)
  + [73. How can I query OHLCV data filtered by specific coins and exchanges using the REST API?](/general/faq/Market-Data-API/#73-how-can-i-query-ohlcv-data-filtered-by-specific-coins-and-exchanges-using-the-rest-api)
  + [74. Why does the REST API return an empty array for OHLCV data instead of a 550 error?](/general/faq/Market-Data-API/#74-why-does-the-rest-api-return-an-empty-array-for-ohlcv-data-instead-of-a-550-error)
  + [75. What are the benefits of using the CoinAPI WebSocket SDK?](/general/faq/Market-Data-API/#75-what-are-the-benefits-of-using-the-coinapi-websocket-sdk)
  + [76. What data is delivered using CoinAPI’s local sites?](/general/faq/Market-Data-API/#76-what-data-is-delivered-using-coinapis-local-sites)
  + [77. What market symbol types are supported by CoinAPI?](/general/faq/Market-Data-API/#77-what-market-symbol-types-are-supported-by-coinapi)
  + [78. What should I do if I encounter missing price data or data gaps?](/general/faq/Market-Data-API/#78-what-should-i-do-if-i-encounter-missing-price-data-or-data-gaps)
  + [79. What is the typical latency of CoinAPI's REST Market Data API?](/general/faq/Market-Data-API/#79-what-is-the-typical-latency-of-coinapis-rest-market-data-api)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.