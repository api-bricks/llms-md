FinFeedAPI Blog - Tutorial: Extracting Key Information from SEC Filings with FinFeedAPI's /v1/extractor Endpoint

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fef86f7d148c1fa9e1d0e5d8f813414bc6e06d15c-1440x1800.webp&w=96&q=75)Maciej

June 03, 2025

Tutorial: Extracting Key Information from SEC Filings with FinFeedAPI's /v1/extractor Endpoint
==============================================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fbdb8ea70d1914a91f530e94d6598536894a1dc39-920x400.png%3Fw%3D920%26h%3D400&w=1920&q=75)

[SEC](https://www.finfeedapi.com/learn/glossary/sec) filings are packed with details about public companies, but finding specific pieces of information can sometimes feel like searching for a needle in a haystack. The FinFeedAPI's `/v1/extractor` endpoint offers a way to get structured, itemized content directly from these filings, making your analysis more efficient.

This tutorial will guide you through using this endpoint, particularly useful for forms like 8-K (which report significant corporate events) and 10-K (annual reports) where information is organized into specific items.

**What You'll Learn:**

* How to make requests to the `/v1/extractor` endpoint using Python.
* The structure of the JSON data returned by the API.
* How to access the content of specific items within a filing (e.g., Item 5.02 from an 8-K or Item 1A from a 10-K).

**Prerequisites:**

* Python 3.x installed.
* The `requests` library is generally useful, but this tutorial will use the `api-bricks-sec-api-rest` Python library provided for the FinFeedAPI.
* Your FinFeedAPI key.

Let's begin.

### Step 1: Setup Your Python Environment

First, ensure you have the `api-bricks-sec-api-rest` library installed. If not, you can install it using pip:

```
1# Step 1: Setup Your Python Environment (Installation)
2pip install api-bricks-sec-api-rest
```

Now, let's import the necessary libraries and configure the API client with your key.

```
1# Step 1: Setup Your Python Environment (Imports and Configuration)
2import api_bricks_sec_api_rest
3import json # For pretty printing JSON responses
4import pandas as pd # For potentially displaying lists of items
5
6# --- API Configuration ---
7# IMPORTANT: Replace "YOUR_API_KEY_HERE" with your actual FinFeedAPI key.
8API_KEY = "YOUR_API_KEY_HERE"
9api_client_config = api_bricks_sec_api_rest.Configuration()
10api_client_config.api_key['Authorization'] = API_KEY
11
12# Initialize the API client object
13api_client = api_bricks_sec_api_rest.ApiClient(configuration=api_client_config)
14
15print("API client configured.")
```

*Explanation*: This section handles the initial setup. We install the FinFeedAPI client library and then import it along with `json` for easier viewing of API responses and `pandas` for potentially structuring lists of items. The `api_client` is initialized with your personal API key.

### Step 2: Obtain an Accession Number

The `/v1/extractor` endpoint requires an `accession_number` to identify the specific SEC filing you want to process. An accession number is a unique identifier assigned by the SEC to each filing.

For this tutorial, we'll use a couple of example accession numbers:

* An 8-K filing (e.g., for Microsoft, CIK: 789019): `0000950170-24-058043` (This 8-K reports Item 5.02 - Departure of Directors or Certain Officers; Election of Directors; Appointment of Certain Officers; Compensatory Arrangements of Certain Officers).
* A 10-K filing (e.g., for Apple, CIK: 320193): `0000320193-23-000106` (This is Apple's annual report for the fiscal year ended September 30, 2023).

In a real application, you might get accession numbers by first querying the `/v1/filings` endpoint based on company CIK, form type, and date ranges.

```
1# Step 2: Obtain an Accession Number
2# Example Accession Numbers
3accession_number_8k = "0000950170-24-058043" # Microsoft 8-K
4accession_number_10k = "0000320193-23-000106" # Apple 10-K
5
6print(f"Using 8-K Accession Number: {accession_number_8k}")
7print(f"Using 10-K Accession Number: {accession_number_10k}")
```

*Explanation*: We've defined two example accession numbers. You can replace these with any valid accession number for a filing you're interested in.

### Step 3: Using the `/v1/extractor` Endpoint

The `/v1/extractor` endpoint is a GET request that takes the `accession_number` as a query parameter. It retrieves the HTML content of the filing and classifies it into relevant item categories.

Let's make a call to this endpoint for our example 8-K filing.

```
1# Step 3: Using the /v1/extractor Endpoint (for 8-K)
2# Initialize the ContentExtractionApi
3extraction_api = api_bricks_sec_api_rest.ContentExtractionApi(api_client)
4
5filing_extract_result_8k = None
6print(f"\nAttempting to extract full structure for 8-K filing: {accession_number_8k}")
7
8try:
9    # Call the API
10    api_response_8k = extraction_api.v1_extractor_get(accession_number=accession_number_8k)
11    
12    if api_response_8k:
13        filing_extract_result_8k = api_response_8k
14        print(f"Successfully extracted data for {filing_extract_result_8k.accession_number}, Form Type: {filing_extract_result_8k.form_type}")
15        if filing_extract_result_8k.items:
16            print(f"Found {len(filing_extract_result_8k.items)} items in this filing.")
17        else:
18            print("No items found in the extracted data for this filing.")
19    else:
20        print(f"No data returned from extractor for {accession_number_8k}.")
21
22except api_bricks_sec_api_rest.ApiException as e:
23    print(f"API Exception when calling /v1/extractor for 8-K: {e}")
```

*Explanation*: We instantiate `ContentExtractionApi` and then call the `v1_extractor_get` method with the `accession_number` of the 8-K filing. The response, if successful, will be a `DTO.FilingExtractResultDto` object.

### Step 4: Understanding the Extracted Data Structure

The API returns a `DTO.FilingExtractResultDto` object (represented as `filing_extract_result_8k` in our code). This object has the following main attributes:

* `accession_number`: The accession number of the processed filing.
* `form_type`: The type of the filing (e.g., "8-K", "10-K").
* `items`: This is a list where each element is a `DTO.FilingItemDto` object. Each `FilingItemDto` represents a classified section or item from the filing and contains:
  + `item_number`: The identifier of the item (e.g., "1.01", "5.02" for an 8-K; "1A", "7" for a 10-K).
  + `item_title`: A descriptive title for the item.
  + `content`: The HTML content of that specific item.

Let's inspect the items found in our 8-K example:

```
1# Step 4: Understanding the Extracted Data Structure (for 8-K)
2if filing_extract_result_8k and filing_extract_result_8k.items:
3    print("\nItems found in the 8-K filing:")
4    for item in filing_extract_result_8k.items:
5        print("----")
6        print(f"  Item Number: {item.item_number}")
7        print(f"  Item Title: {item.item_title}")
8        # Print a small preview of the content
9        content_preview = item.content[:200] + "..." if item.content and len(item.content) > 200 else item.content
10        print(f"  Content Preview (HTML): {content_preview}")
11    print("----")
12else:
13    print("\nNo items to display from the 8-K filing extract.")
```

*Explanation*: This code iterates through the `items` list from the API response and prints the `item_number`, `item_title`, and a short preview of the HTML `content` for each item.

### Step 5: Practical Example - Accessing Specific Item Content

With the structured data, you can now easily access the content of a specific item you are interested in.

**Example 1: Get content of Item 5.02 from the 8-K**

Item 5.02 in an 8-K often relates to changes in directors or principal officers.

```
1# Step 5: Practical Example - Accessing Specific Item Content (Item 5.02 from 8-K)
2if filing_extract_result_8k and filing_extract_result_8k.items:
3    target_item_number_8k = "5.02" 
4    item_5_02_content = None
5    for item in filing_extract_result_8k.items:
6        if item.item_number == target_item_number_8k:
7            item_5_02_content = item.content
8            print(f"\nSuccessfully found Item {target_item_number_8k}: {item.item_title}")
9            break
10    
11    if item_5_02_content:
12        print(f"\nFull HTML Content of Item {target_item_number_8k} (first 1000 characters):")
13        print(item_5_02_content[:1000] + "..." if len(item_5_02_content) > 1000 else item_5_02_content)
14    else:
15        print(f"\nItem {target_item_number_8k} not found in the 8-K filing {accession_number_8k}.")
16else:
17    print("\nNo extracted items from 8-K to search within.")
```

**Example 2: Get content of Item 1A (Risk Factors) from the 10-K**

Let's repeat the extraction for our Apple 10-K example and get "Item 1A".

```
1# Step 5: Practical Example - Accessing Specific Item Content (Item 1A from 10-K)
2# (Assumes extraction_api is already initialized from Step 3)
3filing_extract_result_10k = None
4print(f"\nAttempting to extract full structure for 10-K filing: {accession_number_10k}")
5try:
6    api_response_10k = extraction_api.v1_extractor_get(accession_number=accession_number_10k)
7    if api_response_10k:
8        filing_extract_result_10k = api_response_10k
9        print(f"Successfully extracted data for {filing_extract_result_10k.accession_number}, Form Type: {filing_extract_result_10k.form_type}")
10    else:
11        print(f"No data returned from extractor for {accession_number_10k}.")
12except api_bricks_sec_api_rest.ApiException as e:
13    print(f"API Exception when calling /v1/extractor for 10-K: {e}")
14
15if filing_extract_result_10k and filing_extract_result_10k.items:
16    target_item_number_10k = "1A" # Item 1A for Risk Factors in 10-K
17    item_1a_content = None
18    item_1a_title = ""
19
20    for item in filing_extract_result_10k.items:
21        # Check for "1A" or "Item 1A" to be more flexible
22        if item.item_number and (item.item_number.strip().upper() == "1A" or "ITEM 1A" in item.item_number.strip().upper()):
23            item_1a_content = item.content
24            item_1a_title = item.item_title
25            print(f"\nSuccessfully found Item {item.item_number}: {item_1a_title}")
26            break
27            
28    if item_1a_content:
29        print(f"\nHTML Content of {item_1a_title} (first 1000 characters):")
30        print(item_1a_content[:1000] + "..." if len(item_1a_content) > 1000 else item_1a_content)
31    else:
32        print(f"\nItem 1A (Risk Factors) not found in the 10-K filing {accession_number_10k}.")
33else:
34    print("\nNo extracted items from 10-K to search within.")
```

*Explanation*: These examples show how to loop through the extracted `items` and select one based on its `item_number`. The `content` attribute gives you the HTML for that section. For the 10-K, we search for "1A" or "Item 1A" to be a bit more robust.

### Step 6: Tips for Working with Extracted Content

* **HTML Parsing**: The `content` field for each item is typically HTML. If you need to extract plain text, specific figures from tables, or further process the structure within an item, you'll need to use an HTML parsing library like `BeautifulSoup` in Python. This tutorial focuses on retrieving the itemized HTML; further parsing is a subsequent step.
* **Item Number Variations**: While the API attempts to classify items, be aware that there can sometimes be slight variations in how item numbers are reported in filings (e.g., "1A" vs. "Item 1A"). Your code might need to handle such cases if you are looking for very specific items across many different filings. The `/v1/extractor/item` endpoint (covered in other FinFeedAPI documentation/tutorials) is designed to fetch a single item and might have more normalization for these variations.
* **Large Content**: Some items, like MD&A or full financial statements within an exhibit, can be very large. Be mindful of this when processing or storing the content.

### Conclusion

The FinFeedAPI's `/v1/extractor` endpoint is a valuable tool for developers needing to programmatically access specific, categorized sections of SEC filings. By providing a structured JSON output with itemized content, it greatly simplifies the task of pinpointing relevant information within these often lengthy and complex documents.

From here, you could:

* Automate the extraction of specific items from a list of filings (obtained via the `/v1/filings` endpoint).
* Feed the extracted HTML content into NLP pipelines for textual analysis.
* Build applications that alert users to specific events based on the content of 8-K items.

Happy coding with the FinFeedAPI!

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