FinFeedAPI Blog - Understanding Market Data: Levels 1, 2, and 3 Explained To Developers

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fef86f7d148c1fa9e1d0e5d8f813414bc6e06d15c-1440x1800.webp&w=96&q=75)Maciej

April 14, 2025

Understanding Market Data: Levels 1, 2, and 3 Explained To Developers
=====================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F7557c007023326fe39d89ed18844aa4f525a5458-1920x1280.jpg%3Frect%3D0%2C223%2C1920%2C835%26w%3D920%26h%3D400&w=1920&q=75)

Market data is fundamental for developers building financial and trading solutions. It enables accurate tracking of prices, trading volume, and order flows. For developers creating financial software, accessing varying depths of data significantly impacts the quality of their applications.

Here, we'll explore Level 1, Level 2, and Level 3 data, highlighting their differences, use cases, and importance.

[What is Market Data](https://www.finfeedapi.com/blog/stock-market-data-realtime-intraday-historical) in Stock Trading?
-----------------------------------------------------------------------------------------------------------------------

Market data consists of trading-related information for various [securities](https://www.finfeedapi.com/learn/glossary/security), including the latest commodity price, trading volume, highest and lowest prices, and sales data. Trading professionals rely on it to make informed decisions, determine trading strategies, and identify trends.

![ai generated, stock market, graph, stock, upward trend, upside, money, economy, investment, success, growth, stock market, stock market, stock market, stock market, stock market](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fab648d7e440b1ec4456b94a929165bc522618ce4-1280x1280.png&w=1920&q=75)

[Level 1 Market Data](https://www.finfeedapi.com/learn/glossary/level-1-data): Basic Information
------------------------------------------------------------------------------------------------

Level 1 provides fundamental information, typically including:

* Current price of a commodity
* [Best bid](https://www.finfeedapi.com/learn/glossary/best-bid-and-offer-bbo) (current best bid)
* Best ask
* Trading volume

This level provides users with **essential up-to-date information**, suitable for most casual stock exchange fans and applications requiring basic stock trading insights.

### Common Uses of Level 1 Data

Level 1 is ideal for:

* Retail investors
* Casual traders
* Financial applications providing basic price tracking
* Technical charts displaying stock prices

It helps identify general conditions on the exchange and offers a quick snapshot of stock performance.

Although useful, Level 1 lacks depth. It doesn't provide visibility into different price levels or the complete order book, limiting the ability to see the complete situation of listed securities and identify large outstanding or hidden orders.

Level 2 Market Data: Greater Depth, Insights and Market Maker ID
----------------------------------------------------------------

**Level 2 market data offers a detailed view,** extending beyond the current best bid and ask into other indicators. It displays additional information, like multiple price levels for bids and asks, providing deeper insights.

Traders can leverage Level 2 data to their advantage by analyzing market depth, determining the time of trades, and identifying levels of support and resistance.

### Components of Level 2 Data

Key aspects of Level 2 market data include:

* Bid and ask prices at various levels
* Sizes of orders at each level
* Market maker ID information

Level 2 data offers bid prices and other price quotes from market makers, emphasizing the credibility and legitimacy of the market makers involved.

Market maker IDs in Level 2 market data help identify the activities of particular market makers, indicating potential pressure to buy or sell. This visibility can influence trading strategies, especially when whale orders appear.

### DOM Window and Level 2 Data

The Depth of Market (DOM) window visualizes Level 2 data by presenting all active bid prices and ask prices alongside order sizes. Developers creating financial tools use it extensively to display a clear, comprehensive snapshot of market depth. This detailed information enables tracking market maker behavior and gain insights into potential price movements.

Despite its depth, Level 2 data doesn’t fully disclose order identities or intentions, which can sometimes hide large orders . Traders may still encounter hidden orders, making the DOM window less transparent in situations involving high liquidity or large, hidden transactions.

### Using Level 2 Data in Trading Strategies

Day traders heavily rely on Level 2 data for:

* Identifying support and resistance levels
* Detecting hidden orders or attempts to hide large orders
* Tracking levels of prices and how liquid stocks are
* Spotting trends and predicting stock price movements

**Traders should be cautious when interpreting Level 2 data**, as large orders can be canceled before execution, creating misleading signals about market support.

For example, traders monitoring low liquidity stocks use Level 2 data to gauge demand and liquidity by observing the number and sizes of outstanding orders.

### Level 2 Data in Action: An Example

Imagine a highly liquid stock. Level 2 market data indicates substantial bid volume at specific levels, suggesting strong support. Conversely, heavy ask volume at higher levels signifies resistance.

Users leverage this information to refine entry and exit points. However, it does not necessarily guarantee that the displayed order sizes and price levels will reflect the trades executed.

Level 3 Market Data: Complete Transparency
------------------------------------------

**Level 3 data delivers the most comprehensive view**, often exclusive to market makers and institutions. It includes detailed order book information including orders which are open, identifying traders by name and showcasing order intentions explicitly.

### Components of Level 3 Data

Level 3 data includes:

* Detailed open [order book](https://www.finfeedapi.com/learn/glossary/order-book)
* Complete bid and ask details
* Trader identities
* Outstanding order intentions

This transparency allows institutional traders to gauge precise conditions on the exchange accurately, along with other indicators available in Level 3 data .

### Use Cases for Level 3 Data

Level 3 data serves primarily:

* Market makers
* Institutional traders
* Advanced algorithmic trading applications

They are using Level 3 data directly to observe other participants' order intentions. Such explicit transparency facilitates precise trading strategies, minimizing guesswork around order execution.

### Level 3 Data in Action: An Example

Consider an institutional trader monitoring a stock experiencing significant [volatility](https://www.finfeedapi.com/learn/glossary/volatility). With Level 3, they access the complete order book, clearly viewing orders which are open, trader identities, and their outstanding order intentions.

For instance, a large institution plans to sell a substantial position and places a significant sell order at a certain level. With Level 3 visibility, other participants immediately see this intention, prompting reactions such as adjusting their own bids or sells accordingly.

This full transparency helps institutional traders anticipate substantial moves by other players and strategically time their trades to optimize execution and minimize market impact.

![A flat-design infographic titled "Market Data Levels Comparison" displays three vertically stacked sections representing different levels of financial market data:  Level 1: Basic Data — Shows a single stock price with best bid and ask prices and trading volume. Use cases include casual investors and basic financial apps. Labeled with "Depth: Low."  ⬇️ Arrow pointing down to indicate progression.  Level 2: Detailed Insights — Displays a list of multiple bid/ask levels with sizes and market maker IDs. Intended for active traders and detailed chart analysis. Labeled with "Depth: Medium."  ⬇️ Another arrow pointing down.  Level 3: Full Transparency — Shows a complete book with trader identities and open order intentions. Geared toward institutional trading and algorithms. Labeled with "Depth: High."  The design uses a clean blue-and-white color palette, simple icons, and bold headings to emphasize the increasing complexity and use cases from Level 1 to Level 3.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fbf466bc0e4308b8eb27599623b093f319c9caf2f-1024x1536.png&w=1920&q=75)

Why Developers Need Level 2 and [Level 3 Data](https://www.finfeedapi.com/learn/glossary/level-3-data)
------------------------------------------------------------------------------------------------------

Developers building trading solutions **must have access to Level 2 and potentially Level 3 data** for several reasons:

* Enhancing accuracy of trading algorithms
* Offering advanced analytical tools
* Improving liquidity assessment capabilities

Level 2 data allows developers to identify the sources of orders through the 'market by broker' view, providing insights into trading activity from different participants.

High-quality financial software often depends on deeper insights into prices , providing competitive advantages through improved order execution and trading efficiency.

> **"Building powerful financial solutions starts with access to accurate, detailed information —empower your application with transparency."**

### Price Levels

Level 2 and Level 3 clearly outline different price levels, showcasing market depth. This helps developers build features to measure liquidity accurately, helping to understanding the real-time demand and supply dynamics.

### Impact on Trading Decisions

With detailed data, trading professionals can better interpret technical charts, identify patterns, and make timely trading decisions. Recognizing action around specific levels enables effective trading strategies, such as buying near support levels or selling near resistance threshold.

### Identifying Support and Resistance Levels

Level 2 data helps to accurately identify support and resistance levels by observing the highest and lowest prices as well as price levels with significant bid and ask volumes. This precise view enables to place informed buy or sell orders.

### Detecting Hidden Orders

Hidden orders remain a challenge, but Level 2 market data helps identify anomalies or large, concealed order sizes, giving an edge in anticipating future moves.

![A 2D digital infographic titled "Detecting Hidden Orders with Level 2 Data" is divided into two horizontal sections:  Top Section (Normal Orders): Displays a standard Level 2 order book with multiple bid and ask levels. Order sizes are consistent and typical across price levels, suggesting regular market activity.  Bottom Section (Hidden Orders): Shows a similar book, but one ask level (e.g., price 101.2) is highlighted in yellow with an unusually large order size compared to surrounding levels. This visual anomaly suggests the presence of a hidden or iceberg order.](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F17b1cb1bc5d23f097adffc1f058a2e9ee28b96aa-1024x1024.png&w=1920&q=75)

### Technical Charts and Price Information

Advanced technical charts often incorporate Level 2 and Level 3 data for low liquidity stocks , displaying comprehensive price information and order flows. This detailed integration helps to visually analyze depth of the market and liquidity.

### Bid and Ask Prices and [Market Depth](https://www.finfeedapi.com/learn/glossary/market-depth)

Bid and ask prices across multiple levels also illuminate market depth, allowing to spot liquidity clusters and make quick decisions based on detailed up-to-date information.

Access to Market Data: Considerations for Developers
----------------------------------------------------

Developers must consider the data depth their solutions require. While Level 1 suffices for basic trades tracking, advanced trading applications demand Level 2 or Level 3 to provide meaningful insights.

Typically, brokers require to pay extra for Level 2 and Level 3 due to their increased detail and utility. Developers should factor these costs into their product design decisions. There are some developer-focused solutions like FinFeedAPI which do not charge extra for access to levels beyond Level 1 - developers should consider prioritizing them to avoid paying exorbitant sums.

Additionally, developers should consider the ability to view market data for different symbols, detailing the best bids and asks associated with each symbol, as well as the depth of the market for ongoing orders.

> **High-quality financial software depends on thorough insights—Level 2 and Level 3 aren’t optional; they're foundational.**

Conclusion
----------

Access to accurate and detailed data significantly influences trading effectiveness. Level 1 serves basic needs, Level 2 provides deeper insights essential for active traders, and Level 3 offers complete transparency for institutional applications.

**Understanding these differences helps developers create targeted, powerful trading solutions that empower users with the necessary tools to succeed.**

![children, win, success, video game, play, happy, macbook, creative, computer, laptop, technology, happiness, portrait, children, children, success, success, success, happy, happy, happy, happy, happy, computer, computer, computer, computer, laptop, technology, technology](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb9bed21e08b6867ff496312020a43a8d24be0cf7-780x470.jpg&w=1920&q=75)

Stay up to date with the latest FinFeedAPI news

Send

By subscribing to our newsletter, you accept our website terms and privacy policy.

### Recent Articles

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Ff5d281796605b6b3d0e45cc56de84fc716102e7c-920x400.png&w=3840&q=75)

Stock market data APIs

Whats a Stock Index: Definition, Types, and Importance in Investing

A stock index is a collection of company shares that tracks the performance of a specific market segment. By combining the prices of selected stocks, it provides a snapshot of market trends and overall performance](/blog/whats-a-stock-index)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F1d11014f03ff374a2c828a2e5b7dbc27dc4db44a-920x400.png&w=3840&q=75)

Stock market data APIs

FinFeedAPI Now Covers the Stock Exchange of Thailand

FinFeedAPI has expanded its data coverage to include the Stock Exchange of Thailand (SET) [XBKK], one of Southeast Asia's most liquid and established markets. This integration provides direct API access to the Thai market, continuing our mission to offer comprehensive global data through a single, developer-friendly interface.](/blog/finfeed-cover-set-stock-exchange-of-thailand)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F1d5b6ba9d9743e616729cd516369d9713549b3b3-920x400.png&w=3840&q=75)

Exchange rates API

Financial Symbols and Their Meanings: A Complete Guide to Global Currency Symbols

Financial symbols and their meanings form the foundation of global economic communication, enabling trillions of dollars in daily transactions across international borders. From the universally recognized dollar sign to emerging cryptocurrency symbols, these visual representations continue evolving alongside our changing global economy.](/blog/financial-symbols-and-their-meanings)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb374c99676570587856b9d56f1c76f9f6a3ec28f-920x400.png&w=3840&q=75)

Stock market data APIs

Essential Stock Market Terms: Complete Guide for Investors in 2025

Whether you’re reading analyst reports, evaluating potential investments, or executing trades, knowing the language of Wall Street is essential. This guide covers the most important stock market terms every investor should master, from basic concepts to advanced strategies that can enhance your investment strategy.](/blog/essential-stock-market-terms)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F819c61799d42674a7cdffa6adba96f22f86d4341-920x400.png&w=3840&q=75)

Stock market data APIs

Ticker Symbol for Stock Market: Complete Guide to Stock Identification

Whether you’re researching your first stock purchase or trying to understand financial news websites, mastering ticker symbols is essential for navigating the stock market effectively. This comprehensive guide will walk you through everything you need to know about these crucial market identifiers.](/blog/ticker-symbol-for-stock-market)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F68905fb6b11d4873535f8eb71d6d915591151ca2-920x400.png&w=3840&q=75)

Exchange rates API

Over 80 New Currencies Added to Currencies API

Our FX Realtime and Historical REST APIs have been updated to support an expanded list of fiat currencies. The service now includes data for over 250 currencies, increasing the geographical scope of available exchange rate data to include more markets across Africa, Asia, Europe, the Americas, and Oceania.](/blog/currencies-api-80-new-currencies)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F576399cd8818961aa8958e890f011c9f77affe8e-920x400.png&w=3840&q=75)

Stock market data APIs

FinFeedAPI Adds Coverage for the Jamaica Stock Exchange (XJAM)

FinFeedAPI has expanded its data coverage to include the Jamaica Stock Exchange (XJAM), providing direct API access to a key Caribbean financial market. This addition is part of our ongoing effort to provide comprehensive, global market data through a single, unified interface.](/blog/finfeedapi-adds-jamaica-stock-exchange)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fded24160df10dcb70b8f4d7103188527f4f5a776-920x400.png&w=3840&q=75)

Stock market data APIs

New Markets, New Opportunities: FinFeedAPI Welcomes Spotlight, New Zealand, and Prague Exchanges

We are excited to share a major update to our data offerings. FinFeedAPI now provides direct API access to three additional European and Asia-Pacific stock exchanges: the Spotlight Stock Market (XSAT), the New Zealand Stock Exchange (XNZE), and the Prague Stock Exchange (XPRA).](/blog/new-exchanges-spotlight-new-zealand-prague)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F918183f3c09da9d691de108abe90afbed1e2a70d-920x400.png&w=3840&q=75)

API technology

API Market Trends: Top Platforms to Buy, Sell, and Integrate APIs

Curious about the API market? This article explores the latest trends, must-know platforms, and how API marketplaces support developers and businesses in the tech ecosystem.](/blog/api-market-trends)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fac972de386f9a1e8586c7eadbb12a39680c68eb9-920x400.png&w=3840&q=75)

API technology

Stop Babysitting Your AI: A Developer’s Guide to Self-Sufficient Financial Agents with MCP APIs

Stop babysitting your AI. Learn how developers can use FinFeedAPI's machine-readable APIs to build autonomous agents that intelligently analyze SEC, stock, and FX data](/blog/self-sufficient-financial-agents-with-mcp-apis)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb9058ff6698f7f327be6f5628681e35092e857a9-920x400.png&w=3840&q=75)

API technology

FinFeed API is compatible with MCP

Your AI just learned to speak finance: Say goodbye to API integration headaches](/blog/finfeed-api-mcp-compability)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F1be57bde0d03d7a664a2dbfc1f0995e1bd7ba109-920x400.png&w=3840&q=75)

Flat files, Stock market data APIs

API vs. Flat File: A Fintech Developer's Grudge Match

Developers, stop guessing. Learn when to use a real-time REST API versus a batch flat file for financial data. Our guide covers security, scalability, and real-world anecdotes.](/blog/api-vs-flat-file)

### Get your free API key now and start building in seconds!

[Get API Key](https://console.finfeedapi.com/?link=/apikeys/create)[Read Docs](https://docs.finfeedapi.com/)

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