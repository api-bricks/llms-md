Flat Files API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/Flat-Files-API/)

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

    - [How to get an estimation for Flat Files data](/general/faq/Flat-Files-API/estimation-for-flat-files)
  + [Exchange Rates API](/general/faq/Exchange-Rates-API/)
  + [Node as a Service](/general/faq/Node-as-a-Service/)
  + [Enterprise Plan](/general/faq/Enterprise-Plan/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [FAQ](/general/faq/)
* Flat Files API

On this page

Flat Files API
==============

Welcome to the CoinAPI FAQ. We've grouped the most common customer questions by product to help you find quick, clear answers.

Tips for Navigating This FAQ[​](/general/faq/Flat-Files-API/#tips-for-navigating-this-faq "Direct link to Tips for Navigating This FAQ")
----------------------------------------------------------------------------------------------------------------------------------------

* Use CTRL+F to search for terms like "order book", "Flat Files", or "credits".
* Bookmark docs.coinapi.io for full technical documentation.

Frequently Asked Questions[​](/general/faq/Flat-Files-API/#frequently-asked-questions "Direct link to Frequently Asked Questions")
----------------------------------------------------------------------------------------------------------------------------------

### 1. What is Flat Files?[​](/general/faq/Flat-Files-API/#1-what-is-flat-files "Direct link to 1. What is Flat Files?")

Flat Files is CoinAPI's service that delivers high-resolution, historical cryptocurrency market data in downloadable CSV format. This product is designed for users who require large-scale data access for offline processing, analytics, or backtesting.

Currently supported data types include:

* Trades
* Quotes
* Full Limit Order Book

These files are ideal for quant researchers, institutions, and analytics platforms that need to handle and analyze deep market data at scale.

Note:

OHLCV data is not included in the Flat Files offering. For time-aggregated candlestick data, please use the Market Data API or aggregate it yourself from trade data available in the Flat Files.

For documentation and pricing:

<https://docs.coinapi.io/flat-files-api/>

### 2. What are the best practices for cost optimization?[​](/general/faq/Flat-Files-API/#2-what-are-the-best-practices-for-cost-optimization "Direct link to 2. What are the best practices for cost optimization?")

To minimize your API and data transfer costs when using CoinAPI’s Flat Files product, follow these proven strategies:

1. Target Specific Symbols or Pairs

   Download only the data relevant to your assets or strategies to reduce file volume and costs.
2. Use Efficient LIST Calls

   Avoid excessive listing operations. If you already know the exact file paths, skip listing and go straight to download.
3. Implement Delta Downloads

   Download only new or updated files since your last sync instead of fetching full datasets repeatedly.
4. Adjust Download Frequency

   Assess how often you really need the data—daily downloads may be overkill for some use cases.
5. Cache Locally

   Store previously downloaded data to avoid duplicate downloads and save on both credits and bandwidth.
6. Monitor & Review Usage

   Use the Customer Portal to review your API credit and data transfer consumption regularly.
7. Bundle Downloads

   Automate and schedule batch downloads during off-peak times or consolidate multiple symbols into fewer requests.

Bonus Tip: Use the Flat Files Estimator Script to forecast file sizes and costs before downloading.

### 3. What data types are available through the Flat Files?[​](/general/faq/Flat-Files-API/#3-what-data-types-are-available-through-the-flat-files "Direct link to 3. What data types are available through the Flat Files?")

CoinAPI's Flat Files product includes the following data types for in-depth historical analysis and low-latency backtesting:

1. Quotes

   Top-of-book data showing the best bid and ask prices and sizes.

   * Double timestamped (by exchange and server)
   * Useful for spread tracking, best-bid-offer (BBO) monitoring, and latency analysis
2. Trades

   Each entry represents a transaction between market participants, including price, size, and aggressor (if available).

   * Double timestamped
   * Ideal for tick-by-tick backtesting and execution analysis
3. Limitbook Full

   Full depth of book (L2 or L3 depending on the exchange), starting with a snapshot followed by all updates.

   * Suitable for reconstructing full market microstructure
   * Preferred by firms running complex simulation or queue analysis models

Note:

OHLCV data is not currently available as part of the Flat Files product. If you need OHLCV data, it can be accessed via the Market Data API or generated client-side from trade data provided in Flat Files.

For details on format, access, and billing, refer to: <https://docs.coinapi.io/flat-files-api/>

### 4. What is the file structure of Flat Files data?[​](/general/faq/Flat-Files-API/#4-what-is-the-file-structure-of-flat-files-data "Direct link to 4. What is the file structure of Flat Files data?")

CoinAPI’s Flat Files are delivered in a standardized directory and file structure using CSV format, compressed with gzip for efficient storage and download.

Each file is structured as follows:

* File format: `.csv.gz` (CSV + GZIP compression)
* Directory structure: Organized by data type, date, exchange, and symbol
* Header row: Present in each CSV file for easy parsing
* Timestamps: Double-timestamped when applicable (exchange and receive time)

How to use the files:

1. Download the `.csv.gz` file using the Flat Files API or your preferred tool
2. Decompress it using a utility like `gzip`, `7-Zip`, or similar
3. Load the CSV file into a spreadsheet, database, or processing script

For full file path patterns, schema definitions, and examples, visit the official documentation:

[Data Types and File Structure Overview](https://docs.coinapi.io/flat-files-api/data-types/)

### 5. What support is available if I encounter issues with Flat Files?[​](/general/faq/Flat-Files-API/#5-what-support-is-available-if-i-encounter-issues-with-flat-files "Direct link to 5. What support is available if I encounter issues with Flat Files?")

CoinAPI provides multiple levels of support for users working with Flat Files:

* Documentation: Comprehensive technical documentation is available to guide you through file structure, usage, data types, billing, and access. Start here: [Flat Files API Docs](https://docs.coinapi.io/flat-files-api/)
* Support Portal: You can submit a ticket through our [Support Portal](https://support.coinapi.io/) for assistance with issues related to file access, API usage, data interpretation, or billing.
* Email Support: All plans include email support. For Enterprise plans, faster response times and custom support options (e.g., Slack channel) are available.
* Error Reporting: When submitting a ticket, include details such as file path, timestamps, exchange, and symbol involved to help us resolve your issue faster.

### 6. What’s the full scope of historical data available via Flat Files?[​](/general/faq/Flat-Files-API/#6-whats-the-full-scope-of-historical-data-available-via-flat-files "Direct link to 6. What’s the full scope of historical data available via Flat Files?")

CoinAPI's Flat Files provide access to high-resolution historical market data in CSV format. The available data types include:

* Trades – All executed trade events with price, size, and timestamp.
* Quotes – Best bid and ask updates (Level 1 order book).
* Full Order Book (`limitbook_full`) – Tick-by-tick updates of the order book at L2/L3 granularity.

Note: OHLCV data is currently not included in the Flat Files product. For time-aggregated candles, please use our Market Data API.

Flat Files support data going back to February 2014, depending on the exchange and symbol.

### 7. How Far Back Does CoinAPI’s Trade (Tick) Data Go?[​](/general/faq/Flat-Files-API/#7-how-far-back-does-coinapis-trade-tick-data-go "Direct link to 7. How Far Back Does CoinAPI’s Trade (Tick) Data Go?")

CoinAPI offers extensive historical tick-level trade data through its Flat Files service—ideal for backtesting, quantitative modeling, and historical research.

Key availability by exchange:

* Binance – From July 14, 2017
* Coinbase Pro (GDAX) – From January 14, 2015
* Kraken – From January 7, 2014

Some legacy data extends back to July 2010, depending on the exchange.

To explore the full scope of available trade data across all supported venues, refer to our [Flat Files API documentation](https://docs.coinapi.io/flat-files-api), or reach out to support for assistance with a specific exchange or symbol.

### 8. Are Flat Files Normalized Across All Exchanges?[​](/general/faq/Flat-Files-API/#8-are-flat-files-normalized-across-all-exchanges "Direct link to 8. Are Flat Files Normalized Across All Exchanges?")

Yes, CoinAPI’s Flat Files are fully normalized across all supported exchanges. Each dataset adheres to a consistent schema, regardless of the data source.

This unified format simplifies:

* Cross-exchange data analysis and backtesting
* Integration with internal systems and tools
* Elimination of exchange-specific parsing or mapping logic

For detailed information on the schema and data format, refer to the [Flat Files API documentation](https://docs.coinapi.io/flat-files-api), or contact support with specific questions.

### 9. Is schema consistency guaranteed across venues and over time?[​](/general/faq/Flat-Files-API/#9-is-schema-consistency-guaranteed-across-venues-and-over-time "Direct link to 9. Is schema consistency guaranteed across venues and over time?")

Yes, CoinAPI guarantees schema consistency across all supported exchanges and historical periods. This ensures that your integrations remain stable over time and your historical analyses stay reliable as the dataset expands.

Key benefits:

* Standardized data structures for all venues and timeframes
* Synchronized timestamps across data types using high-precision time sync
* Confidence in accurate aggregation and comparison across exchanges

For technical specifications, refer to the Flat Files documentation or reach out to support.

### 10. Are Symbol Naming Conventions Standardized?[​](/general/faq/Flat-Files-API/#10-are-symbol-naming-conventions-standardized "Direct link to 10. Are Symbol Naming Conventions Standardized?")

Yes, CoinAPI uses standardized naming conventions for all symbols across its platform to ensure consistency and ease of integration, filtering, and analysis.

Symbol identifier patterns

CoinAPI defines symbol IDs using a structured pattern based on the instrument type:

* SPOT: `{`exchange\_id`}_SPOT_{`asset\_id\_base`}_{`asset\_id\_quote`}`
* FUTURES: `{`exchange\_id`}_FTS_{`asset\_id\_base`}_{`asset\_id\_quote`}_{`YYMMDD of future\_delivery\_time`}`
* OPTIONS: `{`exchange\_id`}_OPT_{`asset\_id\_base`}_{`asset\_id\_quote`}_{`YYMMDD of expiration`}_{`strike\_price`}_{`C/P`}`
* PERPETUALS: `{`exchange\_id`}_PERP_{`asset\_id\_base`}_{`asset\_id\_quote`}`
* INDEXES: `{`exchange\_id`}_IDX_{`index\_id`}`
* CREDIT: `{`exchange\_id`}_CRE_{`asset\_id\_base`}`
* CONTRACTS: `{`exchange\_id`}_COT_{`contract\_id`}`

  If duplicate IDs occur across markets, an additional suffix prefixed with `_` is appended to ensure uniqueness.

  Variable naming

  All variables follow the `snake_case` convention for improved readability and consistent usage across APIs and documentation.

  For further reference:

  + [Flat Files API Naming Standards](https://docs.coinapi.io/flat-files-api/)
  + Market Data API symbol metadata documentation.

  ### 11. How Easy Is It to Integrate Flat Files into a Cloud-Based Data Warehouse?[​](/general/faq/Flat-Files-API/#11-how-easy-is-it-to-integrate-flat-files-into-a-cloud-based-data-warehouse "Direct link to 11. How Easy Is It to Integrate Flat Files into a Cloud-Based Data Warehouse?")

  CoinAPI’s Flat Files are built for seamless integration with cloud-native data infrastructures, thanks to the S3-compatible API and standardized format.

  Key Integration Benefits

  + S3-Compatible API: Fully interoperable with platforms like Amazon Redshift, Google BigQuery, Snowflake, and other data lakes or warehouses
  + ETL-Ready: Works out of the box with major ETL tools (e.g., Apache NiFi, Airbyte, Fivetran)
  + Language-Agnostic SDKs: Available in multiple languages with setup guides and working examples
  + Optimized for Scale: Designed to support high-throughput batch ingestion of large historical datasets

  Integration Overview

  1. Review the [Flat Files API documentation](https://docs.coinapi.io/flat-files-api/) for endpoint structure and data format
  2. Set up the relevant SDKs or S3-compatible client
  3. Configure access credentials (e.g., AWS IAM roles or API keys)
  4. Load data into your warehouse using standard ingestion pipelines

  For advanced help, contact our support team to discuss architecture recommendations or troubleshooting tips.

  ### 12. Do You Offer SDKs or Connectors for Popular Data Tools (e.g., Python, R, Pandas, Spark, Airflow)?[​](/general/faq/Flat-Files-API/#12-do-you-offer-sdks-or-connectors-for-popular-data-tools-eg-python-r-pandas-spark-airflow "Direct link to 12. Do You Offer SDKs or Connectors for Popular Data Tools (e.g., Python, R, Pandas, Spark, Airflow)?")

  Yes, CoinAPI provides official SDKs for a wide range of languages and ecosystems, making it easy to connect with your preferred data tools, platforms, and workflows.

  Supported Languages and Frameworks

  + Python, R, MATLAB
  + Java, C++, C#.NET, Go, PHP
  + JavaScript, TypeScript, Node.js
  + Ruby, Objective-C, Haskell

  These SDKs are well-suited for use with:

  + Pandas and NumPy for in-memory data analysis
  + Apache Spark for distributed data processing
  + Apache Airflow for workflow automation and scheduling

  Open Source & Ready to Use

  Refer to the [SDK Guide](https://docs.coinapi.io/flat-files-api/s3-api/sdk) for each SDK to find installation steps, usage examples, and best practices.

  ### 13. Is There a “Sync” Mechanism for Receiving Updated Flat Files?[​](/general/faq/Flat-Files-API/#13-is-there-a-sync-mechanism-for-receiving-updated-flat-files "Direct link to 13. Is There a “Sync” Mechanism for Receiving Updated Flat Files?")

  Yes, CoinAPI offers both pull-based and automated sync mechanisms to keep your Flat Files data up to date.

  Current: Pull-Based Access via S3-Compatible API

  You can download Flat Files on demand using CoinAPI’s S3-compatible API, perfect for:

  + Custom ingestion schedules
  + Integration with existing S3 clients or scripts
  + Incremental sync logic using directory metadata

  Coming Soon: Push API (Self-Managed)

  CoinAPI will soon offer a Push API feature that enables:

  + Subscription to specific datasets
  + Daily automatic delivery of updated files to your infrastructure
  + Reduced manual effort and polling overhead

  Available Now: Fully Managed Sync for Enterprise Plans

  Enterprise customers can access an automated sync service that:

  + Uploads Flat Files daily to a customer-owned S3 bucket
  + Includes one-time bulk delivery and ongoing file updates
  + Eliminates need for manual file handling

  See the [Flat Files API documentation](https://docs.coinapi.io/flat-files-api) for integration details or contact [support](https://www.coinapi.io/contact) for onboarding.

  ### 14. What Happens If a Flat File Delivery Fails or Is Corrupted? Do You Offer File Validation?[​](/general/faq/Flat-Files-API/#14-what-happens-if-a-flat-file-delivery-fails-or-is-corrupted-do-you-offer-file-validation "Direct link to 14. What Happens If a Flat File Delivery Fails or Is Corrupted? Do You Offer File Validation?")

  If a Flat File download fails or encounters integrity issues, CoinAPI’s S3-compatible API provides detailed diagnostics to help you detect and resolve the problem quickly.

  Error Handling Mechanism

  + HTTP status codes identify issues like missing files, permission errors, or network problems
  + Amazon S3-style XML error messages provide structured responses for automated error handling in your ingestion pipeline

  File Validation & Integrity

  While CoinAPI does not currently expose checksums (e.g., MD5 or SHA) in public metadata:

  + You can implement custom validation logic (e.g., file size thresholds or internal consistency checks)
  + Consider logging and alerting for unexpected variations in file size or format

  For mission-critical ETL workflows, adding a secondary validation layer is recommended.

  Learn more about handling errors and file access in the [Flat Files API documentation](https://docs.coinapi.io/flat-files-api).

  ### 15. What Kind of SLAs or Uptime Guarantees Do You Provide for the REST API and Flat Files?[​](/general/faq/Flat-Files-API/#15-what-kind-of-slas-or-uptime-guarantees-do-you-provide-for-the-rest-api-and-flat-files "Direct link to 15. What Kind of SLAs or Uptime Guarantees Do You Provide for the REST API and Flat Files?")

  CoinAPI offers Service Level Agreements (SLAs) to ensure reliable access to both our REST API and Flat Files endpoints — tailored to your subscription level.

  SLA Coverage Includes:

  + Uptime guarantees for API and Flat File services
  + Access reliability aligned with your plan tier
  + Proactive system monitoring and fast response during incidents

  Custom SLAs for Enterprise Clients

  If you require strict performance guarantees, we offer custom SLA options as part of the Enterprise Plan. These may include:

  + Higher uptime commitments
  + Dedicated infrastructure
  + Third-party-verified performance benchmarks
  + Priority-level support and account management

  To learn more, visit our [Enterprise Plan page](https://www.coinapi.io/pricing) or [contact our support team](https://www.coinapi.io/contact) to discuss your SLA needs.

  ### 16. Is Pricing for Flat Files Volume-Based, Request-Based, or Seat-Based?[​](/general/faq/Flat-Files-API/#16-is-pricing-for-flat-files-volume-based-request-based-or-seat-based "Direct link to 16. Is Pricing for Flat Files Volume-Based, Request-Based, or Seat-Based?")

  Flat Files are priced using a consumption-based model, determined by:

  + API Calls Count – Every call to the Flat Files S3 API counts as one request
  + Data Transfer – Charges are based on the amount of data you retrieve (measured in GB)

  There are no per-user or seat-based fees. You only pay for what you use — making this model scalable for both light and heavy users.

  For full pricing details and examples, refer to the [Flat Files Pricing Page](https://www.coinapi.io/products/flat-files/pricing).

  ### 17. Is there a delay between when data is generated and when Flat Files are available for download?[​](/general/faq/Flat-Files-API/#17-is-there-a-delay-between-when-data-is-generated-and-when-flat-files-are-available-for-download "Direct link to 17. Is there a delay between when data is generated and when Flat Files are available for download?")

  Yes — Flat Files are typically available **after 00:00 UTC** for the **previous day's data**. Availability may vary based on processing time and data volume.

  + Most files are published by **06:00 UTC**
  + Lighter datasets are often available **within a few hours after midnight**

  If your workflow depends on early access, we recommend setting your download window accordingly.

  For timing details and current availability status, see the [Flat Files API documentation](https://docs.coinapi.io/flat-files-api/).

  ### 18. How should I handle `SUB`, `MATCH`, and `ADD` update types in Full Limit Order Book data?[​](/general/faq/Flat-Files-API/#18-how-should-i-handle-sub-match-and-add-update-types-in-full-limit-order-book-data "Direct link to 18-how-should-i-handle-sub-match-and-add-update-types-in-full-limit-order-book-data")

  When processing Full Limit Order Book (LOB) data from CoinAPI, updates reflect changes in market depth and liquidity. Here's how to handle key update types:

  `SUB` / `MATCH` Updates

  + If a `SUB` or `MATCH` update results in `entry_sx` (volume) being less than or equal to zero:

    → Treat this as a `DELETE` event.

    → Remove the order from your local order book.

  This indicates that the order was either fully filled or canceled and no longer exists.

  `ADD` Updates

  + If an `ADD` update is received for a price level that already exists:

    → Accumulate the `entry_sx` with the existing volume at that level.

    → Do not replace the existing value, as you would with a `SET`.

  This ensures your order book reflects the accurate aggregated depth at each price level.

  ### 19. Which CoinAPI product or plan should I choose?[​](/general/faq/Flat-Files-API/#19-which-coinapi-product-or-plan-should-i-choose "Direct link to 19. Which CoinAPI product or plan should I choose?")

  If you're looking for detailed historical bid/ask data—including order book snapshots at specific times, CoinAPI has two key options:

  Option 1: Flat Files (Best for Historical Access & Bulk Analysis)

  + Full Limit Order Book (LOB) Data
    - Captures every change in the order book.
    - Allows you to reconstruct the full order book at any point in time.
  + Quotes Data
    - Provides top-of-book data (best bid/ask prices) over time.
    - Lightweight and efficient for quick backtests or spread analysis.

  Option 2: Market Data API (For Programmatic Access)

  + All predefined plans include historical and live bid/ask and order book data.
  + Choose based on your preferred access protocol:
    - REST API: Good for historical and filtered data
    - WebSocket: Best for real-time streaming
    - FIX API: Ideal for institutional trading setups

  Recommendation:

  + Use Flat Files for downloading a complete historical dataset.
  + Use Market Data API if you want to integrate real-time bid/ask data with selective historical queries into your app or trading system.

  ### 20. How can I purchase and access Flat Files?[​](/general/faq/Flat-Files-API/#20-how-can-i-purchase-and-access-flat-files "Direct link to 20. How can I purchase and access Flat Files?")

  To purchase and start using CoinAPI’s Flat Files (which include historical market data such as trades, quotes, and order books), follow these steps:

  Step 1: Add Usage Credits

  + Log in to your Customer Portal.
  + Navigate to Billing > Add Usage Credits and fund your account using a credit card.
  + To avoid running out of credits, enable Auto Recharge for automatic top-ups.

  Step 2: Create an API Key for Flat Files

  + Go to API Keys in the portal.
  + Click Create Standard API Key.
  + Disable access to all other products and enable only the Flat Files API.

  Credits must be available in your account before you can access the Flat Files.

  Step 3: List & Download Flat Files

  + Refer to the [Flat Files API documentation](https://docs.coinapi.io/flat-files-api/) to explore the S3 API and list available files by exchange, symbol, and date.
  + Optionally, estimate data transfer costs using our Data Transfer Estimation Script (this consumes credits, but you’ll receive $25 in free credits after verifying your payment method and generating an API key).
  + When ready, download the data using the Download Object endpoint.

  Tools Compatibility: The Flat Files API is S3-compatible, meaning you can use common tools like AWS CLI, boto3, or any compatible library or ETL tool for accessing and managing the data.

  Billing: Charges are automatically deducted based on API usage and data transfer volume.

  If you need assistance during setup, feel free to contact our support team.

  ### 21. What is the recommended way to get Size and LastModified metadata for all symbols on a specific exchange and date in Flat Files?[​](/general/faq/Flat-Files-API/#21-what-is-the-recommended-way-to-get-size-and-lastmodified-metadata-for-all-symbols-on-a-specific-exchange-and-date-in-flat-files "Direct link to 21. What is the recommended way to get Size and LastModified metadata for all symbols on a specific exchange and date in Flat Files?")

  The recommended method to retrieve `Size` and `LastModified` metadata for all symbols on a given exchange for a specific day is to perform a daily LIST call using a path prefix such as:

  ```
  mathematica  
    
  T-TRADES/D-{`YYYYMMDD`}/E-HYPERLIQUID/
  ```

  This method returns metadata for each file under that prefix, allowing you to:

  + View file sizes
  + Identify last modified timestamps
  + Filter programmatically to isolate data for your target symbols

  Note: Currently, there is no shortcut to retrieve `Size` or `LastModified` without listing the exact file paths.

  For large-scale automations, consider batching LIST operations and filtering results client-side.

  ### 22. Is there a more cost-effective method (e.g., manifest file, specific API endpoint) to obtain a list of historical files (with Key, Size, LastModified) for an exchange over a date range, to minimize LIST calls when building an initial cache?[​](/general/faq/Flat-Files-API/#22-is-there-a-more-cost-effective-method-eg-manifest-file-specific-api-endpoint-to-obtain-a-list-of-historical-files-with-key-size-lastmodified-for-an-exchange-over-a-date-range-to-minimize-list-calls-when-building-an-initial-cache "Direct link to 22. Is there a more cost-effective method (e.g., manifest file, specific API endpoint) to obtain a list of historical files (with Key, Size, LastModified) for an exchange over a date range, to minimize LIST calls when building an initial cache?")

  Currently, the only available options to retrieve metadata such as `Key`, `Size`, and `LastModified` for historical files in Flat Files are the standard S3-compatible operations: `GET`, `LIST`, and `HEAD` API calls. At this time, we do not provide a manifest file or a dedicated endpoint that allows you to query or fetch this metadata in a more cost-efficient or consolidated manner.

  For the most accurate and up-to-date information, you must perform a `LIST` request to enumerate the available files under a given prefix. This allows you to see what data exists and then selectively `GET` or `HEAD` individual objects if you need additional metadata. While it may not minimize call volume in all cases, batching LIST requests strategically (e.g., by date range or exchange prefix) can help streamline the initial indexing process.

  ### 23. Could you provide an estimated timeframe for when 1-minute OHLCV data will be available via the Flat Files S3 API (`T-OHLCV/` path)? Also, how will the OHLCV period (e.g., 1MIN) be identified in the S3 filenames/paths?[​](/general/faq/Flat-Files-API/#23-could-you-provide-an-estimated-timeframe-for-when-1-minute-ohlcv-data-will-be-available-via-the-flat-files-s3-api-t-ohlcv-path-also-how-will-the-ohlcv-period-eg-1min-be-identified-in-the-s3-filenamespaths "Direct link to 23-could-you-provide-an-estimated-timeframe-for-when-1-minute-ohlcv-data-will-be-available-via-the-flat-files-s3-api-t-ohlcv-path-also-how-will-the-ohlcv-period-eg-1min-be-identified-in-the-s3-filenamespaths")

  At this time, we do not have an estimated release date for when 1-minute OHLCV data will be available in the Flat Files S3 API under the `T-OHLCV/` path. However, we’re actively working to expand our data types and this remains on our roadmap.

  Once available, the OHLCV period (e.g., 1MIN) will be clearly indicated in the S3 file paths or filenames—typically encoded as part of the directory structure or filename convention. We’ll ensure that this follows a consistent pattern for easy parsing.

  We’ll notify all users as soon as this data type becomes accessible.

  ### 24. If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?[​](/general/faq/Flat-Files-API/#24-if-i-wanted-to-just-buy-a-bulk-download-for-lets-say-aergo-usd-from-the-coinbase-exchange-for-the-order-book-data-is-that-possible-or-do-i-have-to-just-loop-through-the-api-to-get-all-the-data "Direct link to 24. If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?")

  Yes, you can purchase daily full-limit order book data for specific trading pairs such as AERGO-USD from the Coinbase exchange via our Flat Files product. This allows you to download bulk historical data without having to loop through API calls.

  Alternatively, if you prefer using the Market Data API, you can access historical order book data using the `date` parameter. However, please note:

  + If you're looking to retrieve data over a range of dates, each day must be requested individually—this applies to both API calls and Flat Files downloads.
  + For API access, using the `date` parameter ensures the complete dataset for that specific day is retrieved.

  For larger date ranges or bulk needs, Flat Files offer a more efficient and cost-effective approach.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Indexes API](/general/faq/Indexes-API/)[Next

How to get an estimation for Flat Files data](/general/faq/Flat-Files-API/estimation-for-flat-files)

* [Tips for Navigating This FAQ](/general/faq/Flat-Files-API/#tips-for-navigating-this-faq)
* [Frequently Asked Questions](/general/faq/Flat-Files-API/#frequently-asked-questions)
  + [1. What is Flat Files?](/general/faq/Flat-Files-API/#1-what-is-flat-files)
  + [2. What are the best practices for cost optimization?](/general/faq/Flat-Files-API/#2-what-are-the-best-practices-for-cost-optimization)
  + [3. What data types are available through the Flat Files?](/general/faq/Flat-Files-API/#3-what-data-types-are-available-through-the-flat-files)
  + [4. What is the file structure of Flat Files data?](/general/faq/Flat-Files-API/#4-what-is-the-file-structure-of-flat-files-data)
  + [5. What support is available if I encounter issues with Flat Files?](/general/faq/Flat-Files-API/#5-what-support-is-available-if-i-encounter-issues-with-flat-files)
  + [6. What’s the full scope of historical data available via Flat Files?](/general/faq/Flat-Files-API/#6-whats-the-full-scope-of-historical-data-available-via-flat-files)
  + [7. How Far Back Does CoinAPI’s Trade (Tick) Data Go?](/general/faq/Flat-Files-API/#7-how-far-back-does-coinapis-trade-tick-data-go)
  + [8. Are Flat Files Normalized Across All Exchanges?](/general/faq/Flat-Files-API/#8-are-flat-files-normalized-across-all-exchanges)
  + [9. Is schema consistency guaranteed across venues and over time?](/general/faq/Flat-Files-API/#9-is-schema-consistency-guaranteed-across-venues-and-over-time)
  + [10. Are Symbol Naming Conventions Standardized?](/general/faq/Flat-Files-API/#10-are-symbol-naming-conventions-standardized)
  + [11. How Easy Is It to Integrate Flat Files into a Cloud-Based Data Warehouse?](/general/faq/Flat-Files-API/#11-how-easy-is-it-to-integrate-flat-files-into-a-cloud-based-data-warehouse)
  + [12. Do You Offer SDKs or Connectors for Popular Data Tools (e.g., Python, R, Pandas, Spark, Airflow)?](/general/faq/Flat-Files-API/#12-do-you-offer-sdks-or-connectors-for-popular-data-tools-eg-python-r-pandas-spark-airflow)
  + [13. Is There a “Sync” Mechanism for Receiving Updated Flat Files?](/general/faq/Flat-Files-API/#13-is-there-a-sync-mechanism-for-receiving-updated-flat-files)
  + [14. What Happens If a Flat File Delivery Fails or Is Corrupted? Do You Offer File Validation?](/general/faq/Flat-Files-API/#14-what-happens-if-a-flat-file-delivery-fails-or-is-corrupted-do-you-offer-file-validation)
  + [15. What Kind of SLAs or Uptime Guarantees Do You Provide for the REST API and Flat Files?](/general/faq/Flat-Files-API/#15-what-kind-of-slas-or-uptime-guarantees-do-you-provide-for-the-rest-api-and-flat-files)
  + [16. Is Pricing for Flat Files Volume-Based, Request-Based, or Seat-Based?](/general/faq/Flat-Files-API/#16-is-pricing-for-flat-files-volume-based-request-based-or-seat-based)
  + [17. Is there a delay between when data is generated and when Flat Files are available for download?](/general/faq/Flat-Files-API/#17-is-there-a-delay-between-when-data-is-generated-and-when-flat-files-are-available-for-download)
  + [18. How should I handle `SUB`, `MATCH`, and `ADD` update types in Full Limit Order Book data?](/general/faq/Flat-Files-API/#18-how-should-i-handle-sub-match-and-add-update-types-in-full-limit-order-book-data)
  + [19. Which CoinAPI product or plan should I choose?](/general/faq/Flat-Files-API/#19-which-coinapi-product-or-plan-should-i-choose)
  + [20. How can I purchase and access Flat Files?](/general/faq/Flat-Files-API/#20-how-can-i-purchase-and-access-flat-files)
  + [21. What is the recommended way to get Size and LastModified metadata for all symbols on a specific exchange and date in Flat Files?](/general/faq/Flat-Files-API/#21-what-is-the-recommended-way-to-get-size-and-lastmodified-metadata-for-all-symbols-on-a-specific-exchange-and-date-in-flat-files)
  + [22. Is there a more cost-effective method (e.g., manifest file, specific API endpoint) to obtain a list of historical files (with Key, Size, LastModified) for an exchange over a date range, to minimize LIST calls when building an initial cache?](/general/faq/Flat-Files-API/#22-is-there-a-more-cost-effective-method-eg-manifest-file-specific-api-endpoint-to-obtain-a-list-of-historical-files-with-key-size-lastmodified-for-an-exchange-over-a-date-range-to-minimize-list-calls-when-building-an-initial-cache)
  + [23. Could you provide an estimated timeframe for when 1-minute OHLCV data will be available via the Flat Files S3 API (`T-OHLCV/` path)? Also, how will the OHLCV period (e.g., 1MIN) be identified in the S3 filenames/paths?](/general/faq/Flat-Files-API/#23-could-you-provide-an-estimated-timeframe-for-when-1-minute-ohlcv-data-will-be-available-via-the-flat-files-s3-api-t-ohlcv-path-also-how-will-the-ohlcv-period-eg-1min-be-identified-in-the-s3-filenamespaths)
  + [24. If I wanted to just buy a bulk download for, let’s say, AERGO-USD from the Coinbase exchange for the order book data, is that possible? Or do I have to just loop through the API to get all the data?](/general/faq/Flat-Files-API/#24-if-i-wanted-to-just-buy-a-bulk-download-for-lets-say-aergo-usd-from-the-coinbase-exchange-for-the-order-book-data-is-that-possible-or-do-i-have-to-just-loop-through-the-api-to-get-all-the-data)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.