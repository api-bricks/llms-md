CoinAPI.io Glossary - Stop Order

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

### Stop Order

A stop order is used to buy or sell a security once its price reaches a specified level, known as the stop price. When the stop price is reached, the stop order becomes a market order and is executed at the best available price.

Table of Contents

* [What is a Stop Order in Crypto Trading?](#link-1cc2256b0176)
* [Types of Stop Orders](#link-912a80cf6212)
* [Stop Order Applications](#link-3c26fbbcc307)
* [Considerations and Risks](#link-3b1f8844c6d7)
* [Things to Remember](#link-5c9f999ff385)

What is a Stop Order in Crypto Trading?
---------------------------------------

A stop order is a trading instruction used to buy or sell a cryptocurrency once its price reaches a predetermined level called the *stop price*. When the stop price is triggered, the stop order becomes a [**market order**](https://www.coinapi.io/learn/glossary/market-order) and is executed at the best available price.

This actual price may differ from the stop price due to market fluctuations. **Stop orders are essential for automating trading strategies, [managing risk](https://www.coinapi.io/learn/glossary/risk-management), and taking advantage of market movements without constant monitoring**.

Types of Stop Orders
--------------------

There are two primary types of stop orders available on trading platforms:

1. **Stop Limit Order**
   * **Functionality:** When the cryptocurrency's price reaches the specified stop price, a **[limit order](https://www.coinapi.io/learn/glossary/limit-order)** is placed at a user-defined price.
   * **Use Case:** Ideal for traders who want to control the exact price at which their order is executed. This prevents unexpected price fluctuations from affecting the trade.
   * **Example:** If Crypto X is trading at $5 and you set a Stop Limit Order with a stop price of $4 and a limit price of $3.90, the system will place a sell limit order at $3.90 once the price drops to $4
2. **Stop Market Order**
   * **Functionality:** Upon reaching the stop price, a market order is executed immediately at the best available price.
   * **Use Case:** Suitable for traders prioritizing the execution of the order over the exact price. This ensures the trade is completed swiftly.
   * **Example:** If Crypto X is trading at $5 and you set a stop market order with a stop price of $4, the system will sell Crypto X at the next available market price once it hits $4.

Stop Order Applications
-----------------------

* **Risk management:** Stop orders are commonly used to limit potential losses. For instance, a trader holding Crypto X at $5 might place a stop-sell order at $4 to automatically exit the position if the market moves unfavorably.
* **Profit Protection:** Traders can also use stop orders to secure profits. If Crypto X appreciates to $6, a stop-sell order at $5.50 helps lock in gains while allowing for further upside.
* **[Algo trading](https://www.coinapi.io/learn/glossary/algo-trading):** By setting stop orders, traders can automate their buy and sell decisions based on predefined price levels. This enables them to take advantage of market movements even when not actively monitoring the market.

Considerations and Risks
------------------------

* **Execution Price Variability:** While market orders ensure order execution, the final trade price may differ from the stop price due to rapid market changes.
* **Partial Fills:** In the case of Stop Limit Orders, there is a risk that the limit price may not be met, resulting in the order not being fully executed.
* **Volatility:** During highly volatile periods, the actual execution price can significantly differ from the stop price, potentially leading to unexpected outcomes.

Things to Remember
------------------

* **Automated risk management:** Stop orders allow traders to set predefined exit points, helping to manage potential losses without constant market monitoring.
* **Choice Between order types:** Understanding the difference between Stop Limit and Stop Market Orders is crucial. Each serves different trading objectives and risk appetites.
* **Execution Risks:** Volatility can impact the final execution price of stop orders. This might lead to prices that differ from the intended stop price.
* **Strategic Profit Protection:** Utilizing stop orders to secure profits ensures that gains are locked in even if the market reverses direction unexpectedly.

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