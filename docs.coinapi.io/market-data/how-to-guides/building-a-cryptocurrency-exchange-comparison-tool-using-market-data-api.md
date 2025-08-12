Building a cryptocurrency exchange comparison tool using Market Data API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api)

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
* Building a cryptocurrency exchange comparison tool using Market Data API

On this page

Building a cryptocurrency exchange comparison tool using Market Data API
========================================================================

If you want to develop a tool for comparing cryptocurrency prices across different exchanges using our [Market Data API](https://www.coinapi.io/market-data-api), follow these simple steps.

1. **API Integration**

   Integrate our Market Data API into your application to access real-time data from diverse cryptocurrency
   exchanges simply by configuring the [API KEY](https://www.coinapi.io/get-free-api-key).
2. **Fetch Data**

   Our API provides data such as the current price, trading volume, and historical prices of different cryptocurrencies across multiple exchanges.

   Within this how-to guide, we'll use the [current quotes endpoint](https://docs.coinapi.io/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol) to obtain the present asset price across diverse exchanges.

info

Quote refers to the current price at which a particular asset is bought or sold on a specific exchange.

3. **Data Comparison**

After acquiring the data, you can compare prices for a specific asset across various exchanges and showcase them.
This could prove beneficial for analyzing trends.

Cryptocurrency exchange comparison tool in Python[​](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api#cryptocurrency-exchange-comparison-tool-in-python "Direct link to Cryptocurrency exchange comparison tool in Python")
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Let’s put the theory into practice.
Here’s an example of comparing real-time prices based on current `quotes`
with our [Market Data API](https://www.coinapi.io/market-data-api) in Python.

1. Import the necessary libraries and set up your API key.

```
import requests  
import json  
  
api_key = 'YOUR_API_KEY'
```

2. Define the `PriceInformation` class to store price data.

```
class PriceInformation:  
    def __init__(self, symbol, price, size, taker_side):  
        self.symbol = symbol  
        self.price = price  
        self.size = size  
        self.taker_side = taker_side
```

3. Define the function to fetch price information for a given coinapi symbol via the [current quotes](https://docs.coinapi.io/market-data/rest-api/quotes/current-quotes-for-a-specific-symbol) endpoint.

```
def get_price(coinapiSymbol):  
    url = f'https://rest.coinapi.io/v1/quotes/{coinapiSymbol}/current?apikey={api_key}'  
    response = requests.get(url)  
    data = json.loads(response.text)  
    last_trade = data.get('last_trade', {})  
    if last_trade:  
        price = last_trade.get('price', '')  
        size = last_trade.get('size', '')  
        taker_side = last_trade.get('taker_side', '')  
        return PriceInformation(coinapiSymbol, price, size, taker_side)  
    return None
```

info

Refer to our metadata documentation for the complete list of [coinapi symbols](https://docs.coinapi.io/market-data/rest-api/metadata/list-of-symbols-for-the-exchange)
available on the specified exchange.

info

4. Define the function to fetch price information for two symbols.

```
def fetch_prices_for_symbols(symbol1, symbol2):  
    priceSymbol1 = get_price(symbol1)  
    priceSymbol2 = get_price(symbol2)  
    return priceSymbol1, priceSymbol2
```

5. Call `fetch_prices_for_symbols` to retrieve price `BTC/USDT` AND `ETH/USDT` on `KRAKEN` and `BINANCE`.

```
# Example usage 1  
priceInfo1, priceInfo2 = fetch_prices_for_symbols('KRAKEN_SPOT_BTC_USDT', 'BINANCE_SPOT_BTC_USDT')  
print(f'Price on [{priceInfo1.symbol}] is [{priceInfo1.price}], based on the last [{priceInfo1.taker_side}] with a size of [{priceInfo1.size}]')  
print(f'Price on [{priceInfo2.symbol}] is [{priceInfo2.price}], based on the last [{priceInfo2.taker_side}] with a size of [{priceInfo2.size}]')  
  
# Example usage 2  
priceInfo3, priceInfo4 = fetch_prices_for_symbols('KRAKEN_SPOT_ETH_USDT', 'BINANCE_SPOT_ETH_USDT')  
print(f'Price on [{priceInfo3.symbol}] is [{priceInfo3.price}], based on the last [{priceInfo3.taker_side}] with a size of [{priceInfo3.size}]')  
print(f'Price on [{priceInfo4.symbol}] is [{priceInfo4.price}], based on the last [{priceInfo4.taker_side}] with a size of [{priceInfo4.size}]')
```

6. Output of the script.

```
> Price on [KRAKEN_SPOT_BTC_USDT] is [67739.9], based on the last [BUY] with a size of [0.00469343]  
> Price on [BINANCE_SPOT_BTC_USDT] is [67791.98], based on the last [SELL] with a size of [0.00168]  
> Price on [KRAKEN_SPOT_ETH_USDT] is [3531.67], based on the last [BUY] with a size of [0.00290074]  
> Price on [BINANCE_SPOT_ETH_USDT] is [3532.58], based on the last [BUY] with a size of [0.0002]
```

7. Here's a complete Python script encompassing all the preceding steps.

```
import requests  
import json  
  
# Set up your API key  
api_key = 'YOUR_API_KEY'  
  
# Define the PriceInformation class to store price data  
class PriceInformation:  
    def __init__(self, symbol, price, size, taker_side):  
        self.symbol = symbol  
        self.price = price  
        self.size = size  
        self.taker_side = taker_side  
  
# Function to fetch price information for a given symbol  
def get_price(coinapiSymbol):  
    url = f'https://rest.coinapi.io/v1/quotes/{coinapiSymbol}/current?apikey={api_key}'  
    response = requests.get(url)  
    data = json.loads(response.text)  
    last_trade = data.get('last_trade', {})  
    if last_trade:  
        price = last_trade.get('price', '')  
        size = last_trade.get('size', '')  
        taker_side = last_trade.get('taker_side', '')  
        return PriceInformation(coinapiSymbol, price, size, taker_side)  
    return None  
  
# Function to fetch prices for two symbols  
def fetch_prices_for_symbols(symbol1, symbol2):  
    priceSymbol1 = get_price(symbol1)  
    priceSymbol2 = get_price(symbol2)  
    return priceSymbol1, priceSymbol2  
  
# Example usage 1  
priceInfo1, priceInfo2 = fetch_prices_for_symbols('KRAKEN_SPOT_BTC_USDT', 'BINANCE_SPOT_BTC_USDT')  
print(f'Price on [{priceInfo1.symbol}] is [{priceInfo1.price}], based on the last [{priceInfo1.taker_side}] with a size of [{priceInfo1.size}]')  
print(f'Price on [{priceInfo2.symbol}] is [{priceInfo2.price}], based on the last [{priceInfo2.taker_side}] with a size of [{priceInfo2.size}]')  
  
# Example usage 2  
priceInfo3, priceInfo4 = fetch_prices_for_symbols('KRAKEN_SPOT_ETH_USDT', 'BINANCE_SPOT_ETH_USDT')  
print(f'Price on [{priceInfo3.symbol}] is [{priceInfo3.price}], based on the last [{priceInfo3.taker_side}] with a size of [{priceInfo3.size}]')  
print(f'Price on [{priceInfo4.symbol}] is [{priceInfo4.price}], based on the last [{priceInfo4.taker_side}] with a size of [{priceInfo4.size}]')
```

Here's a simplified way to fetch the current price for a given asset using the `quotes endpoint` and present it for comparison.

To access the `last 100 quotes` instead of just the current one, you can utilize our [quotes/latest endpoint](https://docs.coinapi.io/market-data/rest-api/quotes/latest-data).

In a real-world scenario, additional functionalities such as error handling, data formatting, and data storage for analysis would be necessary.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react)[Next

Creating a historical crypto price chart using CoinAPI and D3.js](/market-data/how-to-guides/creating-historical-crypto-price-chart-using-CoinAPI-and-D3-js)

* [Cryptocurrency exchange comparison tool in Python](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api#cryptocurrency-exchange-comparison-tool-in-python)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.