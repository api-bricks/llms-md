CoinAPI.io Glossary - Trailing-Stop-Order

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

### Trailing-Stop-Order

A Trailing Stop Order is a dynamic type of stop order that moves with the market price when it's moving in your favor, but stays fixed when the market moves against you.

Table of Contents

* [What is a Trailing-Stop-Order?](#link-888047767e72)
* [How Trailing-Stop-Orders Work](#link-0ce6aacd7c40)
* [Key Parameters](#link-92ffed443d23)
* [Purpose and Advantages](#link-983708fa8997)
* [Practical Application and Example](#link-24d4d2bb6f51)
* [Setting the Right Trailing Offset](#link-8332e848e657)
* [Market Psychology and Trailing Stops](#link-c19757c4c571)
* [Things to Remember](#link-877f668055ee)

What is a Trailing-Stop-Order?
------------------------------

A trailing-stop-order is an advanced type of stop-loss order that adjusts based on the asset's price movement. Unlike traditional stop-loss orders set at a fixed price, this [**order type**](https://www.coinapi.io/learn/glossary/order-type) moves with the market price. They maintain a specified distance either as a percentage or a fixed dollar amount from the asset's highest or lowest price since the order was placed. This strategy allows traders to lock in profits while staying invested as long as the market trend remains favorable.

How Trailing-Stop-Orders Work
-----------------------------

Trailing-stop-orders monitor the asset's price and adjust the stop level accordingly. For a long position, the **trailing stop is set below the current market price and moves upward as the price increases**. If the asset's price declines by the trailing offset from its peak, a [market order](https://www.coinapi.io/learn/glossary/market-order) is triggered to sell the asset. Conversely, for a short position, the trailing stop is placed above the current market price and moves downward as the price decreases. If the price rises by the trailing offset from its lowest point, a market order is executed to cover the short position.

Key Parameters
--------------

When setting up a trailing-stop-order, two crucial parameters must be defined:

* **Trailing Offset**: This specifies the distance between the current market price and the stop price. It can be set as a percentage (e.g., 5%) or a fixed dollar amount (e.g., $1,000). The trailing offset determines how much the price can move against the position before the [stop-order](https://www.coinapi.io/learn/glossary/stop-order) is triggered.
* **Order Quantity**: This represents the total amount of the asset you intend to buy or sell when the stop-order is executed. It ensures that the correct volume is traded once the trailing stop condition is met.

Purpose and Advantages
----------------------

Trailing stop orders are used to protect gains and limit potential losses without requiring constant market monitoring. They allow [trades](https://www.coinapi.io/learn/glossary/trades) to remain open and continue to profit as long as the price moves in a favorable direction. If the market reverses by the specified trailing offset, the order automatically triggers a market sell or buy. This secures profits or minimizes losses. The automation provides traders with a balance between staying invested and managing risk.

Practical Application and Example
---------------------------------

Consider an investor who purchases 1 BTC at $20,000 and sets a trailing stop sell order with a 5% trailing offset. If the BTC price rises to $22,000, the trailing stop adjusts to $20,900 (5% below $22,000). Should the price then decline to $20,900, the trailing stop is triggered, and a market order is executed to sell 1 BTC, securing a profit of $900. Conversely, if the BTC price falls to $18,000 and then rises to $18,900 (5% above the lowest point), the order triggers at $18,900, allowing the investor to exit the position with a minimized loss.

Setting the Right Trailing Offset
---------------------------------

Choosing an appropriate trailing offset is critical for the effectiveness of trailing stop orders. An offset that is too tight may lead to premature triggering due to normal market fluctuations, resulting in unnecessary trades. Conversely, an offset that is too wide may not provide adequate protection against significant losses. Traders often adjust the trailing offset based on market volatility. Wider stops are preferred in [volatile](https://www.coinapi.io/learn/glossary/volatility) markets, while tighter stops are suitable for more stable conditions.

Market Psychology and Trailing Stops
------------------------------------

Understanding market psychology can enhance the strategic use of trailing stops. During temporary price dips, it's essential to resist the urge to reset the trailing stop. Resetting may lead to setting a lower stop-loss than intended, increasing potential losses. Additionally, adjusting the trailing stop when momentum peaks can help lock in profits before a possible trend reversal. Maintaining the trailing stop parameters ensures consistent [risk management](https://www.coinapi.io/learn/glossary/risk-management) and prevents emotional decision-making.

Things to Remember
------------------

* **Dynamic Adjustment**: Trailing-stop-orders automatically adjust with the asset's price movements. This allows traders to lock in profits while staying invested as long as the trend remains favorable. This flexibility helps in capitalizing on upward movements without constant monitoring.
* **Key Parameters**: Setting the appropriate trailing offset and order quantity is essential. The trailing offset determines how much the price can reverse before the stop is triggered. The order quantity ensures the correct volume is executed once the stop condition is met.
* **Types of Orders**: Trailing-stops can be executed as market orders for swift action or limit orders for price control. Understanding the difference helps traders choose the best execution type based on their trading strategy and market conditions.
* **Choosing the Right Offset**: Selecting an appropriate trailing offset based on market volatility is crucial. A too-tight offset may cause premature triggering, while a too-wide offset might not provide sufficient protection. Careful consideration of market dynamics is necessary.

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