Real-time data visualization with javascript | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/real-time-data-visualization-with-javascript)

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
* Real-time data visualization with javascript

On this page

Real-time data visualization with javascript
============================================

Introduction[​](/market-data/how-to-guides/real-time-data-visualization-with-javascript#introduction "Direct link to Introduction")
-----------------------------------------------------------------------------------------------------------------------------------

In this tutorial, we'll demonstrate how to use CoinAPI's WebSockets API alongside `JavaScript` for real-time visualization of cryptocurrency markets.
We'll use `Chart.js`, a popular JavaScript library for data visualization.

Prerequisites[​](/market-data/how-to-guides/real-time-data-visualization-with-javascript#prerequisites "Direct link to Prerequisites")
--------------------------------------------------------------------------------------------------------------------------------------

* Basic understanding of JavaScript and WebSockets.
* A CoinAPI key (obtainable by signing up on the CoinAPI website).
* Familiarity with Chart.js (Visit the Chart.js documentation for more information).

Visualizing Data with Chart.js[​](/market-data/how-to-guides/real-time-data-visualization-with-javascript#visualizing-data-with-chartjs "Direct link to Visualizing Data with Chart.js")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

First, we'll create an empty chart using `Chart.js`.

```
<!DOCTYPE html>  
<html>  
<head>  
	<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>  
    <title>Visualizing Data with Chart.js</title>  
</head>  
<body>  
  
	<canvas id="myChart"></canvas>  
  
    <script>  
		/** part1: chart initialization **/  
		const ctx = document.getElementById('myChart').getContext('2d');  
		const chart = new Chart(ctx, {  
			type: 'line',  
			data: {  
				labels: [], // This will be populated with timestamps  
				datasets: [{  
					data: [], // This will be populated with trade prices  
					label: 'BTC/USD',  
					borderColor: '#3e95cd',  
					fill: false  
				}]  
			},  
			options: {  
				title: {  
					display: true,  
					text: 'Real-Time BTC/USD Trade Prices'  
				}  
			}  
		});  
		  
		/** part2: below we'll establish ws connection and update the chart with real-time data **/  
  
    </script>  
</body>  
</html>
```

The script creates a new line chart with an empty dataset.   
We'll fill in the data as we receive it from the WebSocket connection in the next step.

#### Setting Up the WebSocket Connection[​](/market-data/how-to-guides/real-time-data-visualization-with-javascript#setting-up-the-websocket-connection "Direct link to Setting Up the WebSocket Connection")

We need to set up a WebSocket connection to CoinAPI and update the chart:

```
/** part2: below we establish ws connection and update the chart with real-time data **/  
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
		  
		const data = JSON.parse(event.data);  
		  
		// Add new data to the chart  
		chart.data.labels.push(data.time_exchange);  
		chart.data.datasets[0].data.push(data.price);  
		  
		// Remove the oldest data point if there are more than 50  
		if (chart.data.labels.length > 50) {  
			chart.data.labels.shift();  
			chart.data.datasets[0].data.shift();  
		}  
		  
		// Update the chart  
		chart.update();  
};  
  
socket.onerror = function (error) {  
	console.log(`WebSocket error: ${error}`);  
};
```

**Note:** Don't forget to *replace `YOUR-API-KEY` with your actual API key.*

Here's the complete code:

```
<!DOCTYPE html>  
<html>  
<head>  
	<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>  
    <title>Visualizing Data with Chart.js</title>  
</head>  
<body>  
  
	<canvas id="myChart"></canvas>  
  
    <script>  
		/** part1: chart initialization **/  
		const ctx = document.getElementById('myChart').getContext('2d');  
		const chart = new Chart(ctx, {  
			type: 'line',  
			data: {  
				labels: [], // This will be populated with timestamps  
				datasets: [{  
					data: [], // This will be populated with trade prices  
					label: 'BTC/USD',  
					borderColor: '#3e95cd',  
					fill: false  
				}]  
			},  
			options: {  
				title: {  
					display: true,  
					text: 'Real-Time BTC/USD Trade Prices'  
				}  
			}  
		});  
		  
		/** part2: below we establish ws connection and update the chart with real time data **/  
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
				  
				const data = JSON.parse(event.data);  
				  
				// Add new data to the chart  
				chart.data.labels.push(data.time_exchange);  
				chart.data.datasets[0].data.push(data.price);  
				  
				// Remove the oldest data point if there are more than 50  
				if (chart.data.labels.length > 50) {  
					chart.data.labels.shift();  
					chart.data.datasets[0].data.shift();  
				}  
				  
				// Update the chart  
				chart.update();  
        };  
  
        socket.onerror = function (error) {  
            console.log(`WebSocket error: ${error}`);  
        };  
		  
    </script>  
</body>  
</html>
```

The `onmessage` event is activated whenever a new message (in our case, trade data) is received from the server.   
The message data is in JSON format, which we convert to a JavaScript object with `JSON.parse()`.

Our chart now updates in real time as we receive trade data from CoinAPI!

![Chart.js with CoinAPI real time data](/assets/images/rt-chart-visualization-5d7740b1784355ac60bdfa799f9be778.jpg)

You're now equipped to use CoinAPI with JavaScript for real-time data visualization.   
Dive into the dynamic world of cryptocurrencies and explore with these powerful tools at your disposal.   
Happy coding!

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Import data to Google Sheets/Excel](/market-data/how-to-guides/import-data-to-google-sheets-excel)[Next

Real-time trades stream using WebSocket with different languages](/market-data/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages)

* [Introduction](/market-data/how-to-guides/real-time-data-visualization-with-javascript#introduction)
* [Prerequisites](/market-data/how-to-guides/real-time-data-visualization-with-javascript#prerequisites)
* [Visualizing Data with Chart.js](/market-data/how-to-guides/real-time-data-visualization-with-javascript#visualizing-data-with-chartjs)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.