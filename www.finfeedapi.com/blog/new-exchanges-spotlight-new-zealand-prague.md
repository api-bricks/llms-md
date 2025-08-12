FinFeedAPI Blog - New Markets, New Opportunities: FinFeedAPI Welcomes Spotlight, New Zealand, and Prague Exchanges

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fef86f7d148c1fa9e1d0e5d8f813414bc6e06d15c-1440x1800.webp&w=96&q=75)Maciej

July 11, 2025

New Markets, New Opportunities: FinFeedAPI Welcomes Spotlight, New Zealand, and Prague Exchanges
================================================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fded24160df10dcb70b8f4d7103188527f4f5a776-920x400.png%3Fw%3D920%26h%3D400&w=1920&q=75)

We are excited to share a major update to our data offerings. FinFeedAPI now provides direct API access to three additional European and Asia-Pacific stock exchanges: the [Spotlight Stock Market](https://spotlightstockmarket.com/en/) (XSAT), the [New Zealand Stock Exchange](https://www.nzx.com/) (XNZE), and the [Prague Stock Exchange](https://www.pse.cz/en/) (XPRA).

This update brings you integrated data from the energetic Nordic growth market, New Zealand's established Asia-Pacific hub, and the developing economy of Central and Eastern Europe. We believe offering simple access to these markets helps developers and analysts build more complete and insightful financial tools.

**What This Means for Developers**
----------------------------------

For developers, this update simplifies access to new international markets. You can now integrate data from these exchanges using the same unified REST API you use for all our other markets, saving you the effort of managing different data feeds.

Here is how you can begin using the data from these new exchanges:

* **See Available Markets:** The `/v1/exchanges` endpoint will now include `XSAT`, `XNZE`, and `XPRA` in its response, allowing your application to recognize these new sources.
* **Get a Full List of Symbols:** You can retrieve all tradable securities for an exchange with a call to `/v1/symbols/{exchange_id}`. For example, a request to `/v1/symbols/XNZE` will return the complete list of instruments on the New Zealand Stock Exchange.
* **Analyze Historical Performance:** The `/v1/ohlcv/exchange-symbol/{exchange_id}/{symbol_id}/history` endpoint provides deep historical OHLCV data. This allows for thorough backtesting of trading ideas and the creation of detailed historical charts for your users. You can define the data's time interval, from seconds to years, through the `/v1/ohlcv/periods` endpoint.
* **Track the Latest Data:** To keep your applications current, the `/v1/ohlcv/exchange-symbol/{exchange_id}/{symbol_id}/latest` endpoint provides the most recent [trading data](https://www.finfeedapi.com/blog/stock-market-data-realtime-intraday-historical) available.

**New Horizons for Analysts and Traders**
-----------------------------------------

Traders and analysts can now draw from a wider and more diverse set of global data to find fresh insights.

### **Spotlight Stock Market (XSAT)**

This Swedish-based marketplace is designed for innovative, growing companies. With around 170 listed businesses, it’s a market to watch for emerging companies and new ideas coming out of the Nordic region. For traders, it represents a chance to get in early with companies that have high growth potential.

### **New Zealand Stock Exchange (XNZE)**

As the national exchange of New Zealand, the XNZE offers a look into a mature market with a unique geographic and economic position. It is home to approximately 176 securities, from blue-chip stocks to new growth companies, with a total market capitalization of over NZ$184 billion.

### **Prague Stock Exchange (XPRA)**

The PSE provides a window into the economic pulse of a historic part of Europe. As the largest securities market in the Czech Republic, it lists dozens of companies and is a well-regulated point of entry for investing in the Central and Eastern European region.

**Putting the Data to Work: An Example**
----------------------------------------

Let's walk through a simple scenario to see how you might use this new data. Say you are building a tool to analyze international renewable energy companies.

You could start by calling the `/v1/exchanges` endpoint to find the `exchange_id` for the New Zealand Exchange, `XNZE`. From there, a call to `/v1/symbols/XNZE` would give you the full list of securities. After cross-referencing this list to identify a renewable energy firm, you could retrieve its entire price history with `/v1/ohlcv/exchange-symbol/XNZE/{symbol_id}/history` to chart its long-term performance. To keep your tool up-to-date, you could then make periodic calls to the `/v1/ohlcv/exchange-symbol/XNZE/{symbol_id}/latest` endpoint for recent price action.

We look forward to seeing what you build. [Get your free API key now](https://console.finfeedapi.com/?link=/apikeys/create&_gl=1*1qmpgtv*_gcl_au*NzAwNzYyMjI2LjE3NDY2MTc5NjkuMTEyNzY1ODkwNS4xNzUxMzY4NjU2LjE3NTEzNjg2NTY.) to start exploring these new markets.

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