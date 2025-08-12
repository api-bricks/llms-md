Get Historical OHLCV Data Using CoinAPI | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi)

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
* Get Historical OHLCV Data Using CoinAPI

On this page

Get Historical OHLCV Data Using CoinAPI
=======================================

Introduction[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#introduction "Direct link to Introduction")
------------------------------------------------------------------------------------------------------------------------------

This tutorial guides you through getting historical OHLCV data using CoinAPI.

CoinAPI offers extensive historical data across multiple cryptocurrency markets, which is critical for backtesting trading strategies, performing quantitative research, or even creating visualizations.   
We will cover how to interact with our historical data endpoints using `Python`, `JavaScript`, and `Java`.

Understanding CoinAPI Endpoints[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#understanding-coinapi-endpoints "Direct link to Understanding CoinAPI Endpoints")
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CoinAPI provides several endpoints for accessing historical data, including:

* `ohlcv/period_id/history`: Provides historical OHLCV (Open, High, Low, Close, Volume) data for specified periods.
* `trades/symbol_id/history`: Returns historical trades.
* `quotes/symbol_id/history`: Provides historical quotes.

Remember, you need to replace [period\_Id](/market-data/rest-api/ohlcv#available-periods) and [symbol\_id](/market-data/rest-api/metadata#list-all-symbols-get) with your desired period and symbol respectively.

Python Example[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#python-example "Direct link to Python Example")
------------------------------------------------------------------------------------------------------------------------------------

Using Python, we can use the requests library to interact with CoinAPI. If you don't have the `requests` library installed, you can add it using pip:

```
pip install requests
```

Here's an example:

```
import requests  
  
def fetch_ohlcv():  
    url = "https://rest.coinapi.io/v1/ohlcv/BINANCE_SPOT_ETH_BTC/history?period_id=1MTH&time_start=2023-03-01T00:00:00"  
    headers = { "X-CoinAPI-Key": "YOUR_API_KEY" }  # Replace with your API key  
  
    response = requests.get(url, headers=headers)  
  
    # Check if the response is successful  
    if response.status_code == 200:  
        if response.content:  
            return response.json()  
        else:  
            print("Response is empty.")  
            return None  
    else:  
        # Handle other HTTP status codes  
        print(f"Failed to fetch data. Status code: {response.status_code}")  
        return None  
      
print(fetch_ohlcv())
```

This script fetches the monthly `OHLCV` data for the `ETH/BTC` trading pair from the `BINANCE` exchange.  
Here, `BINANCE` serves as the exchange platform, with `ETH` being the `base asset` and `BTC` as the `quote asset`.

**Note:** Don't forget to *replace `YOUR-API-KEY` with your actual API key.*

JavaScript Example[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#javascript-example "Direct link to JavaScript Example")
------------------------------------------------------------------------------------------------------------------------------------------------

Make sure to install the `nodejs runtime environment` before.  
In JavaScript, we can use the fetch API for sending requests to CoinAPI:

First, add `package.json` with node-fetch dependency:

```
{  
  "type": "module",  
  "dependencies": {  
    "node-fetch": "^3.3.1"  
  }  
}
```

Add the following code and run `npm install` to install dependencies.

```
import fetch from 'node-fetch';  
  
fetch('https://rest.coinapi.io/v1/ohlcv/BINANCE_SPOT_ETH_BTC/history?period_id=1MTH&time_start=2023-03-01T00:00:00', {  
  headers: {  
    "X-CoinAPI-Key": "YOUR_API_KEY" // Replace with your API key  
  }  
})  
.then(response => response.json())  
.then(data => console.log(data))  
.catch(error => console.error('Error:', error));
```

This script fetches the monthly `OHLCV` data for the `ETH/BTC` trading pair from the `BINANCE` exchange.  
Here, `BINANCE` serves as the exchange platform, with `ETH` being the `base asset` and `BTC` as the `quote asset`.

**Note:** Don't forget to *replace `YOUR-API-KEY` with your actual API key.*

Java Example[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#java-example "Direct link to Java Example")
------------------------------------------------------------------------------------------------------------------------------

In Java, we can use the `HttpURLConnection` class to send HTTP requests:

```
import java.net.HttpURLConnection;  
import java.net.URL;  
import java.io.BufferedReader;  
import java.io.InputStreamReader;  
  
public class Main {  
  
    private static final String API_KEY = "YOUR-API-KEY"; // Replace with your API key  
  
    public static void main(String[] args) throws Exception {  
        URL url = new URL("https://rest.coinapi.io/v1/ohlcv/BINANCE_SPOT_ETH_BTC/history?period_id=1MTH&time_start=2023-03-01T00:00:00");  
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();  
        conn.setRequestProperty("X-CoinAPI-Key", API_KEY);  
  
        BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));  
        String inputLine;  
        StringBuffer content = new StringBuffer();  
        while ((inputLine = in.readLine()) != null) {  
            content.append(inputLine);  
        }  
  
        in.close();  
        conn.disconnect();  
  
        System.out.println(content.toString());  
    }  
}
```

This script fetches the monthly `OHLCV` data for the `ETH/BTC` trading pair from the `BINANCE` exchange.  
Here, `BINANCE` serves as the exchange platform, with `ETH` being the `base asset` and `BTC` as the `quote asset`.

**Note:** Don't forget to *replace `YOUR-API-KEY` with your actual API key.*

#### Best Practices[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#best-practices "Direct link to Best Practices")

* `Store API keys securely`: never hard-code API keys. Instead, store them in secure configuration files or environment variables.
* `Handle rate limiting`: be aware of CoinAPI's rate limits and handle 429 HTTP status codes gracefully in your application.
* `Efficient data fetching`: use query parameters like time\_start and limit effectively to get the data you need without excess.

#### Troubleshooting[​](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#troubleshooting "Direct link to Troubleshooting")

In case you face any issues, ensure the following:

* Your API key is correct and has the necessary permissions.
* You are not exceeding the rate limit for your account type.
* You are using the correct endpoint with proper request headers.
* The symbol and period IDs you are using are valid and in the correct format.
* You have the correct libraries or dependencies installed, and you're using a supported version of the language.

For more information, you can check [REST API OHLVC docs](/market-data/rest-api/ohlcv)

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Fetching market data with KNIME](/market-data/how-to-guides/fetching-market-data-with-knime)[Next

Get symbol funding rate metric data using CoinAPI](/market-data/how-to-guides/get-symbol-funding-rate-metric-data)

* [Introduction](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#introduction)
* [Understanding CoinAPI Endpoints](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#understanding-coinapi-endpoints)
* [Python Example](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#python-example)
* [JavaScript Example](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#javascript-example)
* [Java Example](/market-data/how-to-guides/get-historical-ohlcv-data-using-coinapi#java-example)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.