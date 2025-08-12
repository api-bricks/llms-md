[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

### Admin messages

Admin messages are non-trade system notifications sent by an exchange to inform participants about the status of the market, securities, and trading operations.

![background](https://cdn.sanity.io/images/xpx4czto/production/999c709b2777af013884c6e2623e9aa699585a06-429x429.svg)

Table of Contents

* [🧠 Why Admin Messages Matter](#link-f676f3a332ac)
* [🧠 Things to Remember](#link-ff96ca18e250)

While they don’t carry price or order flow data, admin messages are vital for maintaining **synchronization between the exchange and connected participants** — including brokers, data providers, algorithmic systems, and traders. They help inform when a stock is halted, when trading starts or ends, or if a technical issue arises.

Admin messages are part of **real-time market data feeds** and often appear alongside quote and trade messages — especially in **low-latency systems**, such as those using the **ITCH**, **OPRA**, or **FIX** protocols.

⚙️ What Do Admin Messages Communicate?
======================================

Admin messages **control and clarify the trading environment**. Common uses include:

* ⏱️ **Market session updates**: open, close, pre-market, post-market
* ⛔ **Trading halts/resumptions**: due to [volatility](https://www.finfeedapi.com/learn/glossary/volatility), news, or regulatory issues
* 🔄 **Security status changes**: listing, delisting, symbol changes, or [corporate actions](https://www.finfeedapi.com/learn/glossary/corporate-actions)
* ⚠️ **System-level events**: exchange outages, connectivity problems, recovery updates
* 🆕 **New securities**: announcements of IPOs or additions to the platform
* 📝 **Compliance or regulatory flags**: [SEC](https://www.finfeedapi.com/learn/glossary/sec)-related flags, new rules in effect

These messages are **machine-readable** but are also often monitored by human traders — especially during volatile sessions, IPO events, or platform outages.

🧠 Why Admin Messages Matter
---------------------------

While they don’t directly impact price action, **ignoring admin messages can lead to failed orders, execution delays, or regulatory violations**. Algorithmic systems, in particular, use these messages to:

* Pause strategies during halts
* Adjust order logic for symbol changes
* Avoid routing trades during market disruption
* Trigger compliance alerts or reroute trading activity

They’re also essential for **market makers and brokers** to maintain accurate system status and avoid routing orders into inactive or paused securities.

🧠 Things to Remember
--------------------

* **Admin messages don’t move markets**, but they **set the rules of the game**.
* Most trading platforms and APIs **process these messages automatically**, but traders should understand their impact.
* During key market events (e.g., IPOs, halts, earnings), admin messages are essential to **stay aligned with market status**.
* For developers and algo traders: always program your systems to **listen and respond to admin events**, especially halts or trading schedule changes.

[![background](https://cdn.sanity.io/images/xpx4czto/production/8a2788aebc71f7f5dce82eb1b7a5e5cec9a64838-773x184.svg)](/)

###### Join our newsletter

* [![Slack](https://cdn.sanity.io/images/xpx4czto/production/26371f7c1474b3ce9e67c32e006a140ddd704b95-512x512.svg)](https://finfeedapi.slack.com/x-p8539721774929-8529109118914-8531038476964/messages/C08FVM7P68H)
* [![X](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F0aa41878d0ceb77292d9f847b2f4e21d688460c1-2400x2453.png&w=64&q=75)](https://x.com/FinFeedAPI "Follow FinFeedAPI on X")
* [![LinkedIn](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb9ce6f119974543779bbcad7563e234be8edd900-840x779.png&w=64&q=75)](https://www.linkedin.com/company/finfeedapi/?viewAsMember=true "Join FinFeedAPI on LinkedIn")
* [![GitHub](https://cdn.sanity.io/images/xpx4czto/production/f202b6faccfd5cc46299b976c2635fee60b55aa0-98x96.svg)](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi)

###### Products

###### Products

* [Stock API](/products/stock-api)
* [Currencies API](/products/currencies-api)
* [SEC API](/products/sec-api)

###### Use cases

###### Use cases

* [AI agents](/use-case/ai-agents)
* [Backtesting & strategy simulation](/use-case/backtesting-strategy-simulation)
* [Compliance & regulatory monitoring](/use-case/compliance-regulatory-monitoring)
* [E-commerce](/use-case/e-commerce)
* [Financial data platforms](/use-case/financial-data-platforms)
* [Financial education](/use-case/education-platforms)
* [Investment research & analytics](/use-case/investment-research-analytics)
* [Machine learning](/use-case/machine-learning)
* [Market analysis](/use-case/market-analysis)
* [Portfolio management](/use-case/portfolio-management)
* [Remittance](/use-case/remittance)
* [Risk management](/use-case/risk-management)
* [Trading platforms](/use-case/trading-platforms)
* [Travel & hospitality](/use-case/travel-hospitality)

###### Resources

###### Resources

* [Glossary](/learn/glossary)
* [Documentation](https://docs.finfeedapi.com/)
* [Status page](https://status.finfeedapi.com/)
* [SDK](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi)
* [Tutorials](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi/sec-api-rest/tutorials)
* [Brand assets](https://brandfetch.com/finfeedapi.com)

###### Legal

###### Legal

* [Customer agreement](/legal#link-479af90ac5b8)
* [Acceptable usage policy](/legal#link-469068dc1416)
* [Privacy policy](/legal#link-192d9f962f94)

###### Contact

###### Contact

* [Contact us](/contact-us)

###### API Bricks brands

###### API Bricks brands

* [CoinAPI.io](https://www.coinapi.io/?utm_source=finfeedapi&utm_medium=referral&utm_campaign=finfeedapi_footer)

![background](https://cdn.sanity.io/images/xpx4czto/production/33a64ee50c88a79ba86cc35ba36e9eb13987bbe7-152x184.svg)Copyright 2025 API BRICKS LTD or its affiliates. All rights reserved.

FinFeedAPI Glossary - Admin messages