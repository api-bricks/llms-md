FinFeedAPI Glossary - National Best Bid and Offer (NBBO)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

### National Best Bid and Offer (NBBO)

National Best Bid and Offer (NBBO) is a regulatory standard in U.S. equities markets that represents the highest available bid and the lowest available offer (ask) price for a stock across all registered exchanges at any given moment.

![background](https://cdn.sanity.io/images/xpx4czto/production/999c709b2777af013884c6e2623e9aa699585a06-429x429.svg)

Table of Contents

* [National Best Bid and Offer (NBBO)](#link-c98c8636b2fc)
* [Regulation and Compliance](#link-845a9452fbab)
* [Calculation and Dissemination](#link-c7e3f44999fd)
* [Practical Applications](#link-a2e5c34e26e4)
* [Advantages of NBBO](#link-794d73facba0)
* [Disadvantages and Limitations](#link-f641051c612e)
* [NBBO and High-Frequency Trading (HFT)](#link-544a44166144)
* [Example of NBBO in Action](#link-1c3c785d1410)
* [Importance in Market Structure](#link-301bd00169fc)
* [Accessing NBBO Data](#link-5cbb64d0650c)
* [Things to Remember](#link-4d9a7e490b5c)

National Best Bid and Offer (NBBO)
----------------------------------

The **National Best Bid and Offer (NBBO)** is a regulatory standard in U.S. equities markets. It represents the highest available bid price and the lowest available ask price for a stock across all registered exchanges at any moment. This ensures that investors receive the most favorable prices when buying or selling securities. The NBBO aggregates quotes from multiple trading venues, promoting fair and efficient trading.

Regulation and Compliance
-------------------------

Under the Securities Exchange Commission's ([SEC](https://www.finfeedapi.com/learn/glossary/sec)) **Regulation National Market System (Regulation NMS)**, brokers must execute customer orders at the best available bid and ask prices. This regulation ensures that brokers guarantee at least the NBBO price at the time of a trade. It fosters transparency and protects investors from unfavorable pricing.

Calculation and Dissemination
-----------------------------

The NBBO is calculated and disseminated by **Security Information Processors (SIPs)** as part of the National Market System Plan. Two primary SIPs handle this task:

* **Consolidated Quotation System (CQS):** Manages NBBO data for securities listed on the New York Stock Exchange (NYSE), NY-ARCA, and NY-MKT.
* **Unlisted Trading Privileges (UTP) Quote Data Feed:** Handles NBBO data for securities listed on the Nasdaq.

These systems continuously update the NBBO throughout the trading day. They reflect the highest bid and lowest ask prices from all exchanges and market makers. However, certain trading venues like dark pools may not be included due to their opaque nature.

Practical Applications
----------------------

Investors and traders rely on the NBBO to execute trades at the most advantageous prices available across the national market. For example, when a trader places a buy order, the broker routes the order to the exchange offering the lowest ask price from the NBBO. This ensures cost efficiency. Additionally, traders handling large orders can use tools like depth of market data or Level II screens. These tools help identify other potential bid and ask prices beyond the NBBO for optimal order execution.

Advantages of NBBO
------------------

The **NBBO system** democratizes access to the best available prices. It levels the playing field for retail investors who may lack the resources to continuously seek out the best prices across multiple exchanges. By aggregating quotes, the NBBO simplifies the trading process. This allows for more efficient and transparent transactions.

Disadvantages and Limitations
-----------------------------

Despite its benefits, the NBBO has certain drawbacks:

* **Latency Issues:** The NBBO may not always reflect the most current market data. This can result in trades executed at prices different from investor expectations.
* **Exclusion of Alternative Trading Systems:** Dark pools and other non-transparent trading venues may not be included. This limits the scope of liquidity reflected in the NBBO.
* **Regulatory Challenges:** Enforcing Regulation NMS is complex. The high-speed nature of trading and the absence of recorded NBBO prices make compliance verification difficult.

These limitations can impact **high-frequency traders (HFTs)** who depend on the immediacy and accuracy of price data to execute their strategies effectively.

NBBO and High-Frequency Trading (HFT)
-------------------------------------

High-frequency traders leverage specialized infrastructure to connect directly to exchanges. They process orders at speeds surpassing traditional brokers. HFTs exploit the latency between the calculation and publication of the NBBO. This allows them to execute trades ahead of others, capturing profits from minute price discrepancies. Studies, such as the 2013 University of Michigan research, have highlighted significant profits generated through this strategy. This underscores the competitive arms race in the HFT landscape.

Example of NBBO in Action
-------------------------

Consider a stock for company ABC with the following offers and bids:

* **Offers:**
  + 200 shares at $1,000
  + 300 shares at $1,500
  + 100 shares at $1,800
  + 350 shares at $1,600
* **Bids:**
  + 100 shares at $900
  + 200 shares at $800
  + 150 shares at $950

The **NBBO** for ABC would be $950 ([best bid](https://www.finfeedapi.com/learn/glossary/best-bid-and-offer-bbo)) and $1,000 (best offer). These represent the most favorable prices available to traders within the observed range. This ensures that any trade executed for ABC stock leverages the best possible pricing from the aggregated market data.

Importance in Market Structure
------------------------------

The NBBO is integral to the U.S. equity market’s structure. Mandated by Regulation NMS, it promotes fairness and efficiency. By ensuring that orders are routed to the venues offering the best prices, the NBBO prevents market fragmentation from disadvantaging investors. Real-time updates to the NBBO as orders change within U.S. exchanges maintain the integrity and competitiveness of the market.

Accessing NBBO Data
-------------------

Market participants can subscribe to consolidated market data feeds provided by CTA or UTP to receive real-time NBBO information for all National Market System (NMS) securities.

However, it's important to note that NBBO data does not include quotes from alternative trading systems like dark pools. These venues can be significant liquidity sources for certain stocks.

Things to Remember
------------------

* **Definition of NBBO:** The National Best Bid and Offer represents the highest bid and lowest ask prices across all U.S. exchanges. It ensures investors receive the most favorable trading prices available at any given moment.
* **Regulatory Framework:** Under the SEC’s Regulation NMS, brokers must execute trades at NBBO prices. This promotes transparency and protects investors from unfavorable pricing.
* **Data Calculation and Dissemination:** NBBO data is managed by **Security Information Processors** like the Consolidated Quotation System and the UTP Quote Data Feed. It continuously updates throughout the trading day.
* **Advantages and Limitations:** While the NBBO democratizes access to the best prices and enhances market efficiency, it faces challenges such as latency issues, exclusion of dark pools, and regulatory complexities. These challenges can impact high-frequency trading strategies.

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