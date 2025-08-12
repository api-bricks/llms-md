Quickstart | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/indexes-api/introduction/quickstart)

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

* [Indexes API](/indexes-api/)
* [Introduction](/indexes-api/introduction/)

  + [Purpose and Scope](/indexes-api/introduction/purpose-and-scope)
  + [Key Principles](/indexes-api/introduction/key-principles)
  + [Quickstart](/indexes-api/introduction/quickstart)
  + [Governance and Oversight](/indexes-api/introduction/governance-and-oversight)
* [Index offerings](/category/index-offerings)

  + [Principal Market Price](/indexes-api/index-offerings/primkt-index)
  + [Volume Weighted Average Price](/indexes-api/index-offerings/vwap-index)
  + [Volatility Index](/indexes-api/index-offerings/capivix-index)
* [Introduction](/indexes-api/rest-api/coinapi-indexes-rest-api)
* [WebSocket Index API](/indexes-api/websocket-api/)

  + [Endpoints](/indexes-api/websocket-api/endpoints)
  + [General](/indexes-api/websocket-api/general)
  + [Messages](/indexes-api/websocket-api/messages)
* [Data Inputs and Sources](/indexes-api/data-inputs-and-sources/)
* [Index Calculation Methodologies](/category/index-calculation-methodologies)
* [Eligibility Criteria](/category/eligibility-criteria)
* [Index Maintenance](/category/index-maintenance)
* [Index policies](/indexes-api/index-policies/)
* [Governance](/category/governance)
* [Conflict of Interest Policies](/indexes-api/conflict-of-interest-policies)
* [Use of Expert Judgment](/indexes-api/use-of-expert-judgment)
* [Limitations of the Indexes](/indexes-api/limitations-of-the-indexes)
* [Disclaimer](/indexes-api/disclaimer)
* [MCP API](/indexes-api/mcp)

* [Introduction](/indexes-api/introduction/)
* Quickstart

On this page

CoinAPI Indexes API Quickstart
==============================

This quickstart guide will help you get started with the CoinAPI Indexes API.

Prerequisites[​](/indexes-api/introduction/quickstart#prerequisites "Direct link to Prerequisites")
---------------------------------------------------------------------------------------------------

To follow this tutorial, you'll need:

* A CoinAPI key (sign up at [CoinAPI](https://www.coinapi.io/) if you don't have one)
* curl installed on your system

1. Retrieve Last Index Value[​](/indexes-api/introduction/quickstart#1-retrieve-last-index-value "Direct link to 1. Retrieve Last Index Value")
-----------------------------------------------------------------------------------------------------------------------------------------------

Let's start by fetching the last value for the BTC/USD index using the REST API.

> **Real-World Scenario:** *Valuing Cryptocurrency Assets for Financial Reporting*
>
> Imagine you're conducting a financial audit for a company that holds cryptocurrency assets. You need to determine the current USD value of their Bitcoin(BTC) holdings for an accurate financial statement.

```
curl -H "X-CoinAPI-Key: YOUR_API_KEY" \  
     "https://rest-api.indexes.coinapi.io/v1/indexes/IDX_REFRATE_PRIMKT_BTC_USD/latest"
```

Replace `YOUR_API_KEY` with your actual CoinAPI key.

This request will return the latest value of the BTC/USD index. The response will look similar to this:

```
{  
  "index_id": "IDX_REFRATE_PRIMKT_BTC_USD",  
  "sequence": 2323346,  
  "time_coinapi": "2023-06-01T12:00:00.0000000Z",  
  "value": 27500.12  
}
```

2. Fetch Index Timeseries[​](/indexes-api/introduction/quickstart#2-fetch-index-timeseries "Direct link to 2. Fetch Index Timeseries")
--------------------------------------------------------------------------------------------------------------------------------------

Now, let's retrieve the timeseries data for the ETH/USD index for the last 24 hours with 1-hour intervals.

> **Real-World Scenario:** *Auditing Cryptocurrency Transactions*
>
> Imagine you're an auditor reviewing a company's cryptocurrency transactions. The company claims to have executed a significant ETH/USD trade at a specific time yesterday, stating they achieved an optimal price. To verify this claim and ensure the transaction's fairness, you need to analyze the ETH/USD price movements over the past 24 hours.

```
curl -H "X-CoinAPI-Key: YOUR_API_KEY" \  
     "https://rest-api.indexes.coinapi.io/v1/indexes/IDX_REFRATE_PRIMKT_ETH_USD/timeseries?period_id=1HRS&time_start=2023-06-01T00:00:00&time_end=2023-06-02T00:00:00&limit=24"
```

Replace `YOUR_API_KEY` with your actual CoinAPI key, and adjust the `time_start` and `time_end` parameters to reflect the current date.

The response will contain an array of index values for each hour:

```
[  
  {  
    "index_id": "IDX_REFRATE_PRIMKT_ETH_USD",  
    "sequence": 2323300,  
    "time_period_start": "2023-06-01T00:00:00.0000000Z",  
    "time_period_end": "2023-06-01T01:00:00.0000000Z",  
    "time_open": "2023-06-01T00:00:00.0000000Z",  
    "time_close": "2023-06-01T00:59:59.9999999Z",  
    "value_open": 1850.25,  
    "value_high": 1855.50,  
    "value_low": 1848.75,  
    "value_close": 1852.30  
  },  
  // ... more entries for each hour  
]
```

3. Subscribe to Real-time Index Updates[​](/indexes-api/introduction/quickstart#3-subscribe-to-real-time-index-updates "Direct link to 3. Subscribe to Real-time Index Updates")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Finally, let's use WebSocket to subscribe to real-time updates for both BTC/USD and ETH/USD indexes.

> **Real-World Scenario:** *Market Monitoring*
>
> Imagine you're a cryptocurrency trader seeking a comprehensive view of BTC and ETH prices across the majority of the market. You want to monitor real-time market trends to make informed trading decisions.

First, establish a WebSocket connection:

```
curl -i -N -H "Sec-WebSocket-Version: 13" \  
     -H "Sec-WebSocket-Key: SGVsbG8sIHdvcmxkIQ==" \  
     -H "Connection: Upgrade" \  
     -H "Upgrade: websocket" \  
     -H "Host: ws-api.indexes.coinapi.io" \  
     -H "Origin: http://localhost" \  
     https://ws-api.indexes.coinapi.io
```

After the connection is established, send a subscription message:

```
{  
  "type": "hello",  
  "heartbeat": false,  
  "subscribe_filter_index_id": [  
    "IDX_REFRATE_PRIMKT_BTC_USD",  
    "IDX_REFRATE_PRIMKT_ETH_USD"  
  ]  
}
```

Replace `YOUR_API_KEY` with your actual CoinAPI key.

You'll start receiving real-time index updates for both BTC/USD and ETH/USD. Each update will look similar to this:

```
{  
  "type": "index",  
  "index_id": "IDX_REFRATE_PRIMKT_BTC_USD",  
  "sequence": 2323347,  
  "time_coinapi": "2023-06-01T12:01:00.0000000Z",  
  "value": 27505.50  
}
```

Recap[​](/indexes-api/introduction/quickstart#recap "Direct link to Recap")
---------------------------------------------------------------------------

This quickstart guide demonstrates how to use the CoinAPI Indexes API to retrieve the last index value, fetch timeseries data, and subscribe to real-time index updates. You can build upon these examples to create more complex applications and analyses using the CoinAPI Indexes data.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Key Principles](/indexes-api/introduction/key-principles)[Next

Governance and Oversight](/indexes-api/introduction/governance-and-oversight)

* [Prerequisites](/indexes-api/introduction/quickstart#prerequisites)
* [1. Retrieve Last Index Value](/indexes-api/introduction/quickstart#1-retrieve-last-index-value)
* [2. Fetch Index Timeseries](/indexes-api/introduction/quickstart#2-fetch-index-timeseries)
* [3. Subscribe to Real-time Index Updates](/indexes-api/introduction/quickstart#3-subscribe-to-real-time-index-updates)
* [Recap](/indexes-api/introduction/quickstart#recap)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.