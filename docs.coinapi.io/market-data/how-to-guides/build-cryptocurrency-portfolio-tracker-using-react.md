Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react)

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
* Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI

On this page

Building a Cryptocurrency Portfolio Tracker Using React and CoinAPI
===================================================================

Getting Started with CoinAPI[​](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#getting-started-with-coinapi "Direct link to Getting Started with CoinAPI")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Before diving into the tutorial, ensure you have:

* Created a CoinAPI account and obtained an API key
* Basic familiarity with React and web development

First things first, to make use of CoinAPI, you'll need to create an account and procure an API key. The key is needed to authenticate your application requests. Follow the instructions provided in CoinAPI's Getting Started Guide to set up your account.

Setting Up Your React App[​](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#setting-up-your-react-app "Direct link to Setting Up Your React App")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Begin by creating a new React application. You can do this using the create-react-app command or your preferred method.

`npx create-react-app coinapi-portfolio-tracker-app`

You should have the following project structure:

![Project structure](/assets/images/coinapi-portfolio-tracker-app-structure-947b7ccc7ebba230ffd433a1460d82d0.jpg)

Get into the root of the folder in which package.json resides and check whether the project is compiling & starting:

`npm start`

![Successful compilation message](/assets/images/coinapi-portfolio-tracker-app-compiles-d20378846853bc88f935c34791203ed3.jpg)

Once your app structure is ready and the project successfully compiles, open the `App.js` file.  
Copy and paste the following code into the `App.js` to see the header displaying "CoinAPI Cryptocurrency Portfolio Tracker App".

```
import React, { useState } from 'react';  
function App() {  
  return (  
    <div className="App">  
      <h1>CoinAPI Cryptocurrency Portfolio Tracker App</h1>  
    </div>  
  );  
}  
export default App;
```

Start the application again using `npm start`:

![Cryptocurrency portfolio tracker header](/assets/images/coinapi-portfolio-tracker-app-default-view-edcc0cd7a8eb4c151a1217640f4f7fee.jpg)

Retrieving Your Portfolio Data from CoinAPI[​](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#retrieving-your-portfolio-data-from-coinapi "Direct link to Retrieving Your Portfolio Data from CoinAPI")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

CoinAPI provides the `v1/exchangerate/asset_id_base` endpoint for fetching the latest exchange rates of your assets.  
To request `BTC/USD`, `ETH/USD`, and `XRP/USD` exchange rates from CoinAPI, we'll use **useEffect** hook and **axios module** to retrieve data.  
This hook will fetch the exchange rates when the component mounts and then update the portfolio state.  
Add the following code as part of the `App.js`:

```
import React, { useState } from 'react';  
  
function App() {  
const [portfolio, setPortfolio] = useState([]);  
useEffect(() => {  
    async function fetchExchangeRates() {  
      const assets = ['BTC', 'ETH', 'XRP'];  
      const promises = assets.map(asset =>  
        axios.get(`https://rest.coinapi.io/v1/exchangerate/${asset}/USD?apikey=YOUR_API_KEY`)  
      );  
      const responses = await Promise.all(promises);  
      const exchangeRates = responses.reduce((acc, response, index) => {  
        acc[assets[index]] = response.data.rate;  
        return acc;  
      }, {});  
      setPortfolio(exchangeRates);  
    }  
    fetchExchangeRates();  
  }, []);  
  
  return (  
    <div className="App">  
      <h1>CoinAPI Cryptocurrency Portfolio Tracker App</h1>  
    </div>  
  );  
}  
  
export default App;
```

*Note: Make sure to replace `YOUR_API_KEY` with the API key you have obtained via the CoinAPI website.*

To make exchange rates appear in your web app, update the `return` part with the following code:

```
return (  
    <div className="App">  
     <h1>CoinAPI Cryptocurrency Portfolio Tracker App</h1>  
     <ul>  
        {Object.entries(portfolio).map(([asset, exchangeRate]) => (  
          <li key={asset}>{asset}: {exchangeRate}</li>  
        ))}  
      </ul>  
    </div>  
  );
```

Here's the complete `App.js` code:

```
import React, { useState, useEffect } from 'react';  
import axios from 'axios';  
  
function App() {  
  const [portfolio, setPortfolio] = useState([]);  
  useEffect(() => {  
    async function fetchExchangeRates() {  
      const assets = ['BTC', 'ETH', 'XRP'];  
      const promises = assets.map(asset =>  
        axios.get(`https://rest.coinapi.io/v1/exchangerate/${asset}/USD?apikey=YOUR_API_KEY`  
      );  
      const responses = await Promise.all(promises);  
      const exchangeRates = responses.reduce((acc, response, index) => {  
        acc[assets[index]] = response.data.rate;  
        return acc;  
      }, {});  
      setPortfolio(exchangeRates);  
    }  
    fetchExchangeRates();  
  }, []);  
    
  return (  
    <div className="App">  
     <h1>CoinAPI Cryptocurrency Portfolio Tracker App</h1>  
     <ul>  
        {Object.entries(portfolio).map(([asset, exchangeRate]) => (  
          <li key={asset}>{asset}: {exchangeRate}</li>  
        ))}  
      </ul>  
    </div>  
  );  
}  
export default App;
```

Before starting the application, make sure to install the **axios** module via the `npm install axios` command.   
Then start the application with `npm start` and check out the result:

![View with fetched data](/assets/images/coinapi-portfolio-tracker-app-very-first-view-with-data-97473ea6dd571b78c4ca297feacaf6b5.jpg)

Styling Your Portfolio Tracker[​](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#styling-your-portfolio-tracker "Direct link to Styling Your Portfolio Tracker")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Having fetched your portfolio data, you can now proceed to style your tracker.   
You can use raw CSS or opt for a UI library like Bootstrap or Material UI to enhance the look of your portfolio tracker.   
Here we'll use a CSS styling approach and the following classes: `portfolio`, `portfolio-item`, `asset-name` and `asset-rate`.   
Extend GUI part with `className` attributes values as following:

```
  return (  
    <div className="App">  
     <h1>CoinAPI Cryptocurrency Portfolio Tracker App</h1>  
     <div className="portfolio">  
        {Object.entries(portfolio).map(([asset, exchangeRate]) => (  
          <li key={asset} className="portfolio-item">  
            <span className="asset-name">{asset}/USD:</span>   
            <span className="asset-rate">{exchangeRate}</span>  
          </li>  
        ))}  
      </div>  
    </div>  
  );
```

then update `index.css` with CSS class implementation:

```
.portfolio {  
  padding: 1em;  
}  
  
.portfolio-item {  
  display: flex;  
  align-items: center;  
  font-size: 18px;  
  margin-bottom: 10px;  
}  
  
.asset-name {  
  font-weight: bold;  
  margin-right: 10px;  
  color: #007bff;  
}  
  
.asset-rate {  
  color: #28a745;  
}  
  
.portfolio-item:hover {  
  transform: scale(0.95);  
  transition: transform 0.2s ease-in-out;  
}
```

Retrieve data at regular intervals[​](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#retrieve-data-at-regular-intervals "Direct link to Retrieve data at regular intervals")
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Rather than repeatedly refreshing the application to obtain the most recent exchange rates, we can enhance it to fetch this data at specified intervals and automatically update the view.
To update the exchange rates `every 5 seconds`, you can use the `setInterval` function in React.

```
import React, { useState, useEffect } from 'react';  
import axios from 'axios';  
  
function App() {  
  const [portfolio, setPortfolio] = useState([]);  
  useEffect(() => {  
    async function fetchExchangeRates() {  
      const assets = ['BTC', 'ETH', 'XRP'];  
      const promises = assets.map(asset =>  
        axios.get(`https://rest.coinapi.io/v1/exchangerate/${asset}/USD?apikey=YOUR_API_KEY`)  
      );  
      const responses = await Promise.all(promises);  
      const exchangeRates = responses.reduce((acc, response, index) => {  
        acc[assets[index]] = response.data.rate;  
        return acc;  
      }, {});  
      setPortfolio(exchangeRates);  
    }  
    fetchExchangeRates();  
  
   // Fetch exchange rates every 5 seconds  
   const intervalId = setInterval(fetchExchangeRates, 5000);  
  
   // Clean up the interval when the component unmounts to avoid memory leaks  
   return () => clearInterval(intervalId);  
  
  }, []);  
  
  return (  
    <div className="App">  
     <h1>CoinAPI Cryptocurrency Portfolio Tracker App</h1>  
     <div className="portfolio">  
        {Object.entries(portfolio).map(([asset, exchangeRate]) => (  
          <li key={asset} className="portfolio-item">  
            <span className="asset-name">{asset}/USD:</span>   
            <span className="asset-rate">{exchangeRate}</span>  
          </li>  
        ))}  
      </div>  
    </div>  
  );  
}  
export default App;
```

By following these steps, you'll create a basic cryptocurrency portfolio tracker using React and CoinAPI.   
![Styled portfolio](/assets/images/coinapi-portfolio-tracker-app-very-first-view-with-data-styled-3fb4db556596fd177a542132aa28ae43.jpg)

For more information, you can check [REST API Exchange Rates docs](/market-data/rest-api/exchange-rates)

If you would like the data to be sent to you in real-time, check our [Real-time data visualization with javascript](/how-to-guides/real-time-data-visualization-with-javascript) or [real-time trades stream using WebSocket with different languages](/how-to-guides/real-time-trades-stream-using-websocket-with-different-languages) "how-to" articles.

Happy coding!

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Acquire exchange rates with different programming languages](/market-data/how-to-guides/acquire-exchange-rates-with-different-programming-languages)[Next

Building a cryptocurrency exchange comparison tool using Market Data API](/market-data/how-to-guides/building-a-cryptocurrency-exchange-comparison-tool-using-market-data-api)

* [Getting Started with CoinAPI](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#getting-started-with-coinapi)
* [Setting Up Your React App](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#setting-up-your-react-app)
* [Retrieving Your Portfolio Data from CoinAPI](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#retrieving-your-portfolio-data-from-coinapi)
* [Styling Your Portfolio Tracker](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#styling-your-portfolio-tracker)
* [Retrieve data at regular intervals](/market-data/how-to-guides/build-cryptocurrency-portfolio-tracker-using-react#retrieve-data-at-regular-intervals)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.