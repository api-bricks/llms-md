Understanding Execution Quality in the EMS Trading API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/understanding-execution-quality)

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

* [EMS API](/ems-api/)
* [Authentication](/ems-api/authentication)
* [API limits and billing](/ems-api/api-limits-and-billing-metrics)
* [Managed Cloud REST API](/ems-api/rest-api/rest-api)
* [REST API](/ems-api/managed-cloud-rest-api/managed-cloud-rest-api)
* [WebSocket API](/ems-api/websocket/)
* [FIX API](/ems-api/fix/)
* [SOR - WebSocket API](/ems-api/sor-websocket-api)
* [Understanding Execution Quality](/ems-api/understanding-execution-quality)

* Understanding Execution Quality

On this page

Understanding Execution Quality in the EMS Trading API
======================================================

When trading across multiple exchanges, getting the right price matters just as much as getting a trade done. This guide covers how to evaluate execution quality when using the EMS Trading API, with a focus on price comparison, order handling, and liquidity access.

How to Measure Execution Price Quality?[​](/ems-api/understanding-execution-quality#how-to-measure-execution-price-quality "Direct link to How to Measure Execution Price Quality?")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The real cost of a trade isn’t just the quoted price — it’s the price you actually get when the order fills. There are a few ways to track this:

1. Compare your execution price to market benchmarks

* You can use the [Market Data API](/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol) to pull the latest bid/ask prices and compare them to your fills.
* If you’re working with larger orders, tracking VWAP (Volume Weighted Average Price) over a timeframe can help you see how your price compares to market trends.

2. Look at slippage

* Slippage is the difference between the expected price and the actual execution price. If you’re consistently getting worse prices than expected, it might be worth adjusting your order type or timing.
* The [Order Execution Report](/ems-api/rest-api/get-order-execution-report) helps track this by giving detailed information on order fills.

3. Use historical data for deeper analysis

* The [Historical Order Book API](/market-data/rest-api/order-book/historical-data) lets you check what the order book looked like when your trade was executed.
* This can help you understand whether your order impacted the market price or if better liquidity was available at the time.

How Orders Are Handled and Executed?[​](/ems-api/understanding-execution-quality#how-orders-are-handled-and-executed "Direct link to How Orders Are Handled and Executed?")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Not all orders work the same way, and the EMS Trading API gives you several options to manage execution.

1. Different order types for different needs

* Market orders execute immediately at the best available price, but they can have slippage in volatile conditions.
* Limit orders let you set a maximum (or minimum) price, preventing unexpected execution prices.
* Immediate-or-Cancel (IOC) and Fill-or-Kill (FOK) orders help control partial fills and execution timing.

2. Monitoring and managing open orders

* The [Open Orders API](/ems-api/rest-api/get-open-orders) lets you see active trades and adjust them in real time.
* If market conditions change, you can modify or cancel orders through the [Cancel Order API](/ems-api/rest-api/cancel-order-request).

3. Execution reports for transparency

* Once an order is filled, you can use the [History of Order Changes API](/ems-api/rest-api/history-of-order-changes) to review how the trade was executed.

Liquidity and Smart Order Routing (SOR)[​](/ems-api/understanding-execution-quality#liquidity-and-smart-order-routing-sor "Direct link to Liquidity and Smart Order Routing (SOR)")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

If you’re trading across multiple exchanges, it’s important to know whether you’re getting the best possible price. This is where Smart Order Routing (SOR) comes in.

1. How does SOR work?

* Instead of executing on a single exchange, the EMS Trading API can check multiple venues and route the order where the best price is available.
* The process considers factors like liquidity depth, order book activity, and trade fees.

2. Checking if SOR is working for you

* You can compare your execution prices with market-wide bid/ask spreads to see if your orders are getting better fills.
* The [SOR FAQ](/general/faq/general/How-does-SOR-determine-the-best-exchange-for-order-execution) explains more about how the system selects exchanges.

How to Evaluate EMS Trading API for Your Needs?[​](/ems-api/understanding-execution-quality#how-to-evaluate-ems-trading-api-for-your-needs "Direct link to How to Evaluate EMS Trading API for Your Needs?")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

If you’re testing the EMS API and want to measure its performance, here’s a simple way to start:

1. Place test trades and log execution prices.
2. Use the Market Data API to compare fills against market rates.
3. Track slippage and check order book conditions at the time of execution.
4. Adjust order settings based on results (e.g., limit orders vs. market orders).
5. Test Smart Order Routing (SOR) by executing across multiple exchanges.

If you have specific execution benchmarks you need to meet, these tools should help you measure performance and make adjustments where needed.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

SOR - WebSocket API](/ems-api/sor-websocket-api)

* [How to Measure Execution Price Quality?](/ems-api/understanding-execution-quality#how-to-measure-execution-price-quality)
* [How Orders Are Handled and Executed?](/ems-api/understanding-execution-quality#how-orders-are-handled-and-executed)
* [Liquidity and Smart Order Routing (SOR)](/ems-api/understanding-execution-quality#liquidity-and-smart-order-routing-sor)
* [How to Evaluate EMS Trading API for Your Needs?](/ems-api/understanding-execution-quality#how-to-evaluate-ems-trading-api-for-your-needs)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.