FinFeedAPI Glossary - Greeks

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

### Greeks

The Greeks are a set of risk measures that help traders understand how different factors affect the price of an option. They don’t refer to ancient philosophers — instead, they’re named after Greek letters because each one quantifies a specific type of risk or sensitivity in an option’s price.

![background](https://cdn.sanity.io/images/xpx4czto/production/999c709b2777af013884c6e2623e9aa699585a06-429x429.svg)

Table of Contents

* [📈 Delta: Sensitivity to Price](#link-2568a534530d)
* [⏳ Theta: Time Decay](#link-a6fb58e172ac)
* [📊 Vega: Sensitivity to Volatility](#link-c6dd88207aef)
* [🔁 Gamma: Sensitivity of Delta](#link-740a3398a15b)
* [💰 Rho: Sensitivity to Interest Rates](#link-050c8a803a4a)
* [🧠 The Bottom Line](#link-f81d37f56c2a)

📈 Delta: Sensitivity to Price
-----------------------------

**Delta** measures how much the price of an option is expected to move when the price of the **[underlying asset](https://www.finfeedapi.com/learn/glossary/underlying-asset) changes by $1**. For example, if a call option has a delta of 0.60, the option's price will rise approximately $0.60 for every $1 increase in the underlying stock. Delta also gives you a rough idea of the **probability that an option will expire in the money** — a delta of 0.50 means there's about a 50% chance the option will be profitable at expiration.

⏳ Theta: Time Decay
-------------------

**Theta** measures the **rate at which an option loses value as time passes**, all else being equal. This is also known as “time decay.” Since options have expiration dates, their value declines as that date approaches — especially if they are out-of-the-money. A theta of -0.05 means the option will lose about $0.05 in value each day. Time decay is especially important for options sellers, who profit when options they’ve sold lose value over time.

📊 Vega: Sensitivity to [Volatility](https://www.finfeedapi.com/learn/glossary/volatility)
-----------------------------------------------------------------------------------------

**Vega** tells you how much an option’s price will change when **implied [volatility](https://www.finfeedapi.com/learn/glossary/volatility)** changes by 1 percentage point. Options become more valuable when volatility increases, because there's a greater chance of large price swings in the underlying asset. A vega of 0.10 means the option’s price will rise $0.10 if implied volatility increases by 1%. Traders who expect volatility to rise — such as around earnings announcements — often look for positions with high vega exposure.

🔁 Gamma: Sensitivity of Delta
-----------------------------

**Gamma** measures how much an option’s **delta will change** when the underlying asset moves by $1. It shows how stable your delta is — a higher gamma means delta changes rapidly, which can lead to bigger, faster shifts in an option’s price. Gamma is highest for at-the-money options and tends to drop as the option moves deeper into or further out of the money. Gamma is most relevant to traders managing complex positions or those who need to constantly adjust their hedging.

💰 Rho: Sensitivity to Interest Rates
------------------------------------

**Rho** measures how much the value of an option will change in response to a **1% change in interest rates**. It's the least commonly used Greek in everyday trading, because interest rate changes are less frequent and tend to have a small impact on most standard options. That said, in certain environments — especially when rates are moving quickly — rho can become more important, particularly for long-dated options.

🧠 The Bottom Line
-----------------

The Greeks are essential tools for understanding and managing **options risk**. Each one tells a different part of the story: how the option reacts to price moves, time decay, changes in volatility, and more. While you don’t need to memorize every detail to start trading options, knowing the Greeks helps you **make smarter decisions, avoid surprises, and fine-tune your strategy**.

Options are powerful — and with the Greeks, you have a detailed map of how they behave.

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