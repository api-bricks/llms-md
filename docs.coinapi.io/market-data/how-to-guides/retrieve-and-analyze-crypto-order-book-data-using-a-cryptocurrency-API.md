Retrieve and analyze crypto order book data using a cryptocurrency API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API)

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

* [Market Data API](/market-data/)
* [Authentication](/market-data/authentication)
* [API limits and billing](/market-data/api-limits-and-billing-metrics)
* [Metadata Tables](/market-data/metadata-tables/introduction)
* [REST API](/market-data/rest-api/)
* [Websocket API V1](/market-data/websocket/)
* [Websocket API DS](/market-data/websocket-ds/)
* [JSON RPC](/market-data/jsonrpc-api)
* [FIX API](/market-data/fix/)
* [Latency FAQ](/market-data/latency-faq/)
* [How-to guides](/market-data/how-to-guides/)

  + [Introduction](/market-data/how-to-guides/)
  + [Acquire exchange rates with different programming languages](/market-data/how-to-guides/acquire-exchange-rates-with-different-programming-languages)
  + [Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react)
  + [Building a cryptocurrency exchange comparison tool using Market Data API](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api)
  + [Creating a historical crypto price chart using CoinAPI and D3.js](/market-data/how-to-guides/creating-historical-crypto-price-chart-using-CoinAPI-and-D3-js)
  + [Fetching market data with KNIME](/market-data/how-to-guides/fetching-market-data-with-knime)
  + [Get Historical OHLCV Data Using CoinAPI](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi)
  + [Get symbol funding rate metric data using CoinAPI](/market-data/how-to-guides/get-symbol-funding-rate-metric-data)
  + [Import API into Postman](/market-data/how-to-guides/import-api-into-postman)
  + [Import data to Google Sheets/Excel](/market-data/how-to-guides/import-data-to-google-sheets-excel)
  + [Real-time data visualization with javascript](/market-data/how-to-guides/real-time-data-visualization-with-javascript)
  + [Real-time trades stream using WebSocket with different languages](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages)
  + [Retrieve and analyze crypto order book data using a cryptocurrency API](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API)
* [Performance Testing Guide](/market-data/performance-testing-guide)

* [How-to guides](/market-data/how-to-guides/)
* Retrieve and analyze crypto order book data using a cryptocurrency API

On this page

Retrieve and analyze crypto order book data using a cryptocurrency API
======================================================================

In this tutorial, we will delve into the process of fetching and analyzing cryptocurrency order books using the `Python` programming language and `CoinAPI`.

Agenda🔥:[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#agenda "Direct link to Agenda🔥:")
-----------------------------------------------------------------------------------------------------------------------------------------------

1. Crypto order book basics: Understanding cryptocurrency trading order books.
2. Fetching data: Using CoinAPI and Python to retrieve real-time crypto order book data.
3. Analysis: Interpreting cryptocurrency API data for insights.
4. Visualization: Displaying order book data with Python’s Matplotlib.
5. Metrics calculation: Computing key metrics from cryptocurrency API data.

CoinAPI: The ultimate cryptocurrency API for all your crypto data needs 🚀[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#coinapi-the-ultimate-cryptocurrency-api-for-all-your-crypto-data-needs-rocket "Direct link to coinapi-the-ultimate-cryptocurrency-api-for-all-your-crypto-data-needs-rocket")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Before diving into our guide, let’s take a moment to introduce CoinAPI.
CoinAPI offers easy access to a wide range of financial information, encompassing both live and historical data from various exchanges.

Whether you’re looking for detailed trading data, OHLCV (Open, High, Low, Close, Volume), or specific event information, CoinAPI delivers.
CoinAPI provides crypto order book data, making it one of the best crypto APIs available.

Additionally, our support for multiple data delivery methods,
including REST and WebSocket makes it highly versatile for developers creating trading algorithms or crypto market data visualizations.

Let's Begin 🚀[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#lets-begin- "Direct link to Let's Begin 🚀")
--------------------------------------------------------------------------------------------------------------------------------------------------------------

Harnessing the capabilities of CoinAPI, a robust cryptocurrency API, alongside Python, known for its versatility in data analysis and statistical computing,
we can delve deeply into the nuances of the cryptocurrency market.

We’ll walk you through the steps to fetch and analyze crypto order book data in real time,
leveraging the comprehensive data provided by the cryptocurrency API.

Setting Up the API Request[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#setting-up-the-api-request "Direct link to Setting Up the API Request")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

To fetch real-time order book data, you'll first need an API key from [CoinAPI website](https://www.coinapi.io/).
Once you have it, you can proceed to retrieve the data using Python.

**Fetching the data**

```
import requests  
import json  
  
API_KEY = "YOUR_API_KEY_HERE"  
url = f"https://rest.coinapi.io/v1/orderbooks/current?symbol=KRAKEN_SPOT_BTC_USD&apikey={API_KEY}"  
  
response = requests.get(url)  
  
if response.status_code == 200:  
    # The request was successful  
    data = response.json()  
      
    # Save the data to a file  
    with open("order-books-kraken-spot-btc-usd.json", "w") as file:  
        json.dump(data, file, indent=4)  
    print("Data saved to order-books-kraken-spot-btc-usd.json")  
else:  
    # Handle error cases  
    print(f"Error: Status code {response.status_code}")  
    print(response.text)
```

**Response**

```
{  
    "symbol_id": "KRAKEN_SPOT_BTC_USD",  
    "time_exchange": "2023-11-24T08:26:46.6928657Z",  
    "time_coinapi": "2023-11-24T08:26:46.6928657Z",  
    "asks": [  
        {  
            "price": 37549.1,  
            "size": 19.23618731  
        },  
        {  
            "price": 37549.9,  
            "size": 0.08242079  
        },  
        /// other entries omitted for brevity  
    ],  
    "bids": [  
        {  
            "price": 37549.0,  
            "size": 0.136004  
        },  
        {  
            "price": 37545.1,  
        }  
        /// other entries omitted for brevity  
    ]  
}
```

Data Analysis and Metrics[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#data-analysis-and-metrics "Direct link to Data Analysis and Metrics")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Upon data retrieval, the next step involves data analysis using `Python`.

The obtained data typically represents a snapshot of buy and sell orders in the market at a specific moment.
This data consists of two key components: bids and asks. Bids signify the price levels at which buyers are willing to acquire an asset,
while asks represent the price levels at which sellers are willing to sell it. The difference between the highest bid and the lowest ask is
referred to as the `spread`.

Here is a comprehensive list of common metrics and analytical procedures:

* `Order Book Depth` - visualize the liquidity available at various price levels.
* `Order Imbalance` - analyze the disparity between bids and asks to gain insights into market sentiment.
* `Price Levels` - identify significant price levels characterized by substantial volumes of bids or asks.
* `Market Spread` - compute the current bid-ask spread as an indicator of market liquidity.

### Order Book Depth Visualization[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#order-book-depth-visualization "Direct link to Order Book Depth Visualization")

In this `Python` code, we demonstrate how to visualize the order book depth of a cryptocurrency trading pair using `Matplotlib`.

```
import json  
import matplotlib.pyplot as plt  
  
# Function to read order book data from a JSON  
def read_order_book_data(file_path):  
    with open(file_path, 'r') as file:  
        order_book_data = json.load(file)  
    return order_book_data  
  
file_path = 'order-books-kraken-spot-btc-usd.json'  
  
# Read order book data from the file we've obtained in the previous step  
order_book_data = read_order_book_data(file_path)  
  
# Function to visualize order book depth chart  
def visualize_order_book_depth(order_book_data):  
    bids = order_book_data["bids"]  
    asks = order_book_data["asks"]  
      
    bid_prices = [entry["price"] for entry in bids]  
    bid_sizes = [entry["size"] for entry in bids]  
      
    ask_prices = [entry["price"] for entry in asks]  
    ask_sizes = [entry["size"] for entry in asks]  
      
    plt.figure(figsize=(10, 6))  
    plt.plot(bid_prices, bid_sizes, label="Bids (buyers)", color="green")  
    plt.plot(ask_prices, ask_sizes, label="Asks (sellers)", color="red")  
    plt.xlabel("Price")  
    plt.ylabel("Size")  
    plt.title("Order Book Depth")  
    plt.legend()  
    plt.show()  
  
# Visualize the order book depth  
visualize_order_book_depth(order_book_data)
```

The following visualization is the result of the `Python` script demonstrated above.

![order book depth](/assets/images/order-book-depth-90c601aa1c0074bab64003b9c2bc4363.jpg)

Order Book Depth Visualization:

* is a measure of the quantity of buy and sell orders available for a particular financial asset
* it provides insight into market liquidity and the willingness of traders to buy or sell at different prices
* may be used for trading decisions, as it reveals potential price trends

### Order Imbalance, Price Levels, Market Spread[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#order-imbalance-price-levels-market-spread "Direct link to Order Imbalance, Price Levels, Market Spread")

In this `Python` code, we explore `order imbalance`, `significant bids & asks`,
`market spread` metrics for a `BTC/USD` trading pair.

```
import json  
  
# Function to read order book data from a JSON  
def read_order_book_data(file_path):  
    with open(file_path, 'r') as file:  
        order_book_data = json.load(file)  
    return order_book_data  
  
file_path = 'order-books-kraken-spot-btc-usd.json'  
  
# Read order book data from the file we've obtained in the previous step  
order_book_data = read_order_book_data(file_path)  
  
# Function to calculate order imbalance  
def calculate_order_imbalance(order_book_data):  
    bids = sum(entry["size"] for entry in order_book_data["bids"])  
    asks = sum(entry["size"] for entry in order_book_data["asks"])  
  
    order_imbalance = (bids - asks) / (bids + asks)  
    return order_imbalance  
  
# Function to identify significant price levels  
def identify_significant_price_levels(order_book_data, threshold=50):  
    bids = order_book_data["bids"]  
    asks = order_book_data["asks"]  
      
    significant_bids = [entry for entry in bids if entry["size"] > threshold]  
    significant_asks = [entry for entry in asks if entry["size"] > threshold]  
    return significant_bids, significant_asks  
  
# Function to calculate market spread  
def calculate_market_spread(order_book_data):  
    best_bid = order_book_data["bids"][0]["price"]  
    best_ask = order_book_data["asks"][0]["price"]  
      
    spread = best_ask - best_bid  
    return spread  
  
# Common metrics calculation  
order_imbalance = calculate_order_imbalance(order_book_data)  
significant_price_threshold = 20  
significant_bids, significant_asks = identify_significant_price_levels(order_book_data, significant_price_threshold)  
spread = calculate_market_spread(order_book_data)  
  
print("******************************")  
print("Order Imbalance:", order_imbalance)  
print("***************************")  
print("Significant Bids:", significant_bids)  
print("***************************")  
print("Significant Asks:", significant_asks)  
print("***************************")  
print("Market Spread:", spread)  
print("***************************")
```

**Result**

```
> ******************************  
> Order Imbalance: -0.012400502029283922  
> ***************************  
> Significant Bids: [{'price': 37440.7, 'size': 24.73909889}, {'price': 36451.0, 'size': 25.0}]  
> ***************************  
> Significant Asks: [{'price': 37749.0, 'size': 25.0}, {'price': 37840.0, 'size': 24.08119208}, {'price': 38000.0, 'size': 29.60579175}, {'price': 39000.0, 'size': 21.75395535}, {'price': 40000.0, 'size': 58.28620718}]  
> ***************************  
> Market Spread: 0.09999999999854481  
> ***************************
```

Calculated metrics:

* `order_imbalance` - it measures the difference between the total volume of buy orders and sell orders. It provides insights into the overall market sentiment by indicating whether there is an excess of buying or selling interest.
* `significant_price_threshold` is a predetermined value (set to `20` in this case) used to identify price levels in the order book that are considered significant. It helps traders focus on specific price points that may have a more substantial impact on the market.
* `significant_bids` and `significant_asks` are lists of price levels derived from the order book data that meet or exceed the significant\_price\_threshold. These levels are typically associated with higher trading activity and may be seen as key support and resistance levels.
* `spread` is a metric that calculates the difference between the best bid and best ask prices. It represents the cost of executing a market order and is a fundamental factor for traders to consider when entering or exiting positions.

Summary[​](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#summary "Direct link to Summary")
----------------------------------------------------------------------------------------------------------------------------------------------

This tutorial has equipped you with the knowledge and tools necessary to fetch and analyze cryptocurrency order book data using `CoinAPI` and `Python`.
You've learned how to access real-time order book information, visualize order book depth, and calculate important metrics.

Armed with this understanding, you are now better prepared to explore and navigate
the cryptocurrency markets, enabling you to make more informed trading decisions and develop data-driven trading strategies.

Remember that the cryptocurrency market is highly dynamic, so continuous monitoring and analysis are essential for staying ahead in
this exciting and rapidly evolving space.

Happy trading! 🚀📈💰

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Real-time trades stream using WebSocket with different languages](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages)[Next

Performance Testing Guide](/market-data/performance-testing-guide)

* [Agenda🔥:](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#agenda)
* [CoinAPI: The ultimate cryptocurrency API for all your crypto data needs 🚀](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#coinapi-the-ultimate-cryptocurrency-api-for-all-your-crypto-data-needs-rocket)
* [Let's Begin 🚀](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#lets-begin-)
* [Setting Up the API Request](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#setting-up-the-api-request)
* [Data Analysis and Metrics](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#data-analysis-and-metrics)
  + [Order Book Depth Visualization](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#order-book-depth-visualization)
  + [Order Imbalance, Price Levels, Market Spread](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#order-imbalance-price-levels-market-spread)
* [Summary](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API#summary)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.