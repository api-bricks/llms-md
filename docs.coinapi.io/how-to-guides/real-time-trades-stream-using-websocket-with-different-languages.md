Real-time trades stream using WebSocket with different languages | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages)

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
* Real-time trades stream using WebSocket with different languages

On this page

Real-time trades stream using WebSocket with different languages
================================================================

Introduction[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#introduction "Direct link to Introduction")
-------------------------------------------------------------------------------------------------------------------------------------------------------

This tutorial will guide you on how to subscribe to real-time cryptocurrency market data using CoinAPI.   
We will explore using the WebSocket protocol in `Python`, `JavaScript`, and `Java` to get live market data updates.

Understanding WebSocket Protocol[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#understanding-websocket-protocol "Direct link to Understanding WebSocket Protocol")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CoinAPI provides real-time data through the `WebSocket` protocol.   
WebSocket allows for full-duplex communication channels over a single TCP connection,
making it an excellent choice for live data updates.  
The key endpoint for real-time data is `wss://ws.coinapi.io/v1/`.   
To subscribe to a specific type of data, you need to send a subscription message after the connection is established.

Python Example[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#python-example "Direct link to Python Example")
-------------------------------------------------------------------------------------------------------------------------------------------------------------

In Python, we can use the `websocket-client` library to connect to CoinAPI's WebSocket API.   
If you don't have the `websocket-client` library installed, you can add it using pip:

```
pip install websocket-client
```

Here's an example of real time trade data retrieval:

```
import websocket  
import json  
   
def on_message(ws, message):  
    print(message)  
   
def on_error(ws, error):  
    print(error)  
   
def on_close(ws):  
    print("### closed ###")  
   
def on_open(ws):  
  
    ws.send(json.dumps({  
        "type": "hello",  
        "apikey": "YOUR_API_KEY",  
        "subscribe_data_type": ["trade"],  
        "subscribe_filter_symbol_id": [ "BITSTAMP_SPOT_BTC_USD$", "BITFINEX_SPOT_BTC_USD$" ]  
    }))  
   
ws = websocket.WebSocketApp("wss://ws.coinapi.io/v1",  
                              on_message = on_message,  
                              on_error = on_error,  
                              on_close = on_close)  
ws.on_open = on_open  
ws.run_forever()
```

This script:

* Opens WebSocket connection
* Subscribes to real-time data for `BTC/USD` trading on Bitstamp and Bitfinex **(you may replace with your desired cryptocurrency pair)**
* Prints incoming real-time messages

**Note:** *If `subscribe_filter_symbol_id` is ended with `$` character then the exact match is used instead of prefix match*.

You can check out more [message examples](/market-data/websocket/messages) and [hello message parameters](/market-data/websocket/general#hello-message-parameters).

JavaScript Example[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#javascript-example "Direct link to JavaScript Example")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Make sure to install `nodejs runtime environment` before.  
First, add `package.json` with node-fetch dependency:

```
{  
  "type": "module",  
  "dependencies": {  
    "ws": "^8.13.0"  
  }  
}
```

In JavaScript, you can use WebSocket API:

```
import WebSocket from 'ws';  
  
const socket = new WebSocket('wss://ws.coinapi.io/v1/');  
   
socket.onopen = function (event) {  
  socket.send(JSON.stringify({  
      "type": "hello",  
      "apikey": "YOUR_API_KEY",  
      "subscribe_data_type": ["trade"],  
      "subscribe_filter_symbol_id": [ "BITSTAMP_SPOT_BTC_USD$", "BITFINEX_SPOT_BTC_LTC$" ]  
  }));  
};  
   
socket.onmessage = function (event) {  
  console.log(event.data);  
};  
   
socket.onerror = function (error) {  
  console.log(`WebSocket error: ${error}`);  
};
```

This script:

* Opens WebSocket connection
* Subscribes to real-time data for `BTC/USD` trading on Bitstamp and Bitfinex **(you may replace with your desired cryptocurrency pair)**
* Prints incoming real-time messages

Install dependencies via `npm install` command.   
Execute your program in nodejs runtime environment with `node your-script-name.js` command.

**Note:** *If `subscribe_filter_symbol_id` is ended with `$` character then the exact match is used instead of prefix match*.

You can check out more [message examples](/market-data/websocket/messages) and [hello message parameters](/market-data/websocket/general#hello-message-parameters).

JavaScript in a web browser[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#javascript-in-a-web-browser "Direct link to JavaScript in a web browser")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Here's an example that works directly in a web browser, create `index.html` file, paste the code, and start in a web browser:

```
<!DOCTYPE html>  
<html>  
<head>  
    <title>Realtime Crypto Market Data Example</title>  
</head>  
<body>  
    <script>  
        const socket = new WebSocket('wss://ws.coinapi.io/v1/');  
  
        socket.onopen = function (event) {  
            socket.send(JSON.stringify({  
                "type": "hello",  
                "apikey": "YOUR_API_KEY",  
                "subscribe_data_type": ["trade"],  
                "subscribe_filter_symbol_id": ["BITSTAMP_SPOT_BTC_USD$", "BITFINEX_SPOT_BTC_LTC$"]  
            }));  
        };  
  
        socket.onmessage = function (event) {  
            console.log(event.data);  
			const contentDiv = document.getElementById('content');  
			contentDiv.textContent += event.data;  
        };  
  
        socket.onerror = function (error) {  
            console.log(`WebSocket error: ${error}`);  
        };  
    </script>  
	  
	<div id="content">  
	  
</body>  
</html>
```

Java Example[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#java-example "Direct link to Java Example")
-------------------------------------------------------------------------------------------------------------------------------------------------------

If you're using a Maven project, include `Java-WebSocket` and `JSON` dependencies in your pom.xml file:

```
<dependencies>  
  
    <dependency>  
        <groupId>org.java-websocket</groupId>  
        <artifactId>Java-WebSocket</artifactId>  
        <version>1.5.1</version>  
    </dependency>  
  
    <dependency>  
        <groupId>org.json</groupId>  
        <artifactId>json</artifactId>  
        <version>20210307</version>  
    </dependency>  
      
</dependencies>
```

Here's a Java example that uses `WebSocketClient` and `JSONObject` classes:

```
import org.java_websocket.client.WebSocketClient;  
import org.java_websocket.handshake.ServerHandshake;  
import org.json.JSONArray;  
import org.json.JSONObject;  
import java.net.URI;  
import java.net.URISyntaxException;  
  
public class Main {  
  
    public static void main(String[] args) {  
        try {  
            WebSocketClient socket = new WebSocketClient(new URI("wss://ws.coinapi.io/v1/")) {  
                  
                @Override  
                public void onOpen(ServerHandshake serverHandshake) {  
                    JSONObject message = new JSONObject();  
                    message.put("type", "hello");  
                    message.put("apikey", "YOUR_API_KEY");  
  
                    JSONArray subscribeDataType = new JSONArray();  
                    subscribeDataType.put("trade");  
                    message.put("subscribe_data_type", subscribeDataType);  
  
                    JSONArray subscribeFilterSymbolId = new JSONArray();  
                    subscribeFilterSymbolId.put("BITSTAMP_SPOT_BTC_USD$");  
                    subscribeFilterSymbolId.put("BITFINEX_SPOT_BTC_LTC$");  
                    message.put("subscribe_filter_symbol_id", subscribeFilterSymbolId);  
  
                    this.send(message.toString());  
                }  
  
                @Override  
                public void onMessage(String message) {  
                    System.out.println(message);  
                }  
  
                @Override  
                public void onClose(int code, String reason, boolean remote) {  
                    System.out.println("WebSocket closed");  
                }  
  
                @Override  
                public void onError(Exception ex) {  
                    System.out.println("WebSocket error: " + ex.getMessage());  
                }  
            };  
  
            socket.connect();  
        } catch (URISyntaxException e) {  
            e.printStackTrace();  
        }  
    }  
}
```

This Java program:

* Opens WebSocket connection
* Subscribes to real-time data for `BTC/USD` trading on Bitstamp and Bitfinex **(you may replace with your desired cryptocurrency pair)**
* Prints incoming real-time messages

Best Practices[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#best-practices "Direct link to Best Practices")
-------------------------------------------------------------------------------------------------------------------------------------------------------------

* `Handle connection issues`: internet connections aren't always stable. Implement reconnection logic for robustness.
* `Handle rate limiting`: even for WebSocket connections, CoinAPI has rate limits. Keep track of your message rate.
* `Secure your API Key`: do not hardcode your API key. Make sure it is kept secure, consider using environment variables or secure config files which are not committed to your version control system.

**Note:** *If `subscribe_filter_symbol_id` is ended with `$` character then the exact match is used instead of prefix match*.

You can check out more [message examples](/market-data/websocket/messages) and [hello message parameters](/market-data/websocket/general#hello-message-parameters).

Troubleshooting[​](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#troubleshooting "Direct link to Troubleshooting")
----------------------------------------------------------------------------------------------------------------------------------------------------------------

If you're having issues, double-check the following:

* The API key is correct and has the required permissions.
* The WebSocket endpoint URL is correctly formatted.
* The subscription message contains a valid symbol\_id.
* You have the correct libraries or dependencies installed, and you're using a supported version of the language.

Stay tuned for more tutorials on advanced uses of CoinAPI!

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Real-time data visualization with javascript](/market-data/how-to-guides/real-time-data-visualization-with-javascript)[Next

Retrieve and analyze crypto order book data using a cryptocurrency API](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API)

* [Introduction](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#introduction)
* [Understanding WebSocket Protocol](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#understanding-websocket-protocol)
* [Python Example](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#python-example)
* [JavaScript Example](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#javascript-example)
* [JavaScript in a web browser](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#javascript-in-a-web-browser)
* [Java Example](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#java-example)
* [Best Practices](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#best-practices)
* [Troubleshooting](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages#troubleshooting)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.