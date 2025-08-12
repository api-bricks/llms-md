NaaS API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/naas-api/)

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

* [NaaS API](/naas-api/)
* [Authentication](/naas-api/authentication)
* [API limits and billing](/naas-api/api-limits-and-billing-metrics)
* [Bitcoin](/naas-api/bitcoin/)
* [Ethereum](/naas-api/ethereum/)

* NaaS API

On this page

NaaS API
========

Introduction[​](/naas-api/#introduction "Direct link to Introduction")
----------------------------------------------------------------------

The NaaS API is a software product that provides a set of tools for developers to interact with the blockchain.

It make it easier to interface with blockchains, allowing developers to concentrate on creating apps rather than maintaining the supporting infrastructure.

Technical design[​](/naas-api/#technical-design "Direct link to Technical design")
----------------------------------------------------------------------------------

![naas-api-product](/assets/images/naas-api-product-862ba3ec1033f236eef1d9202b6a5fcd.jpg)

We provide public nodes that act as gateways to popular blockchains, including `Bitcoin`, `Ethereum` and more.
These nodes are accessible through a range of HTTP API endpoints, allowing developers and applications to interact with blockchain data effortlessly.

For a full list of available endpoints click [here](/naas-api#endpoints).

Essentials[​](/naas-api/#essentials "Direct link to Essentials")
----------------------------------------------------------------

* [`Node`](/naas-api/#node) serves as both a server and software component responsible for exposing an API to interact with the blockchain.
* [`Chain`](/naas-api#chain-blockchain) or Blockchain, is a distributed and immutable ledger that records all transactions across a decentralized network.
* [`Network`](/naas-api#network) refers to the entire ecosystem of blockchain participants, including nodes, users, and miners, connected via a specific blockchain protocol.

Endpoints[​](/naas-api/#endpoints "Direct link to Endpoints")
-------------------------------------------------------------

The list of endpoints is available in the documentation for each exchange.

Getting started[​](/naas-api/#getting-started "Direct link to Getting started")
-------------------------------------------------------------------------------

To begin using the NaaS API, you'll need:

* [CoinAPI key](https://www.coinapi.io/market-data-api/pricing) (obtainable by signing up on our website).
* Access an operational Node via any of our [endpoints](/naas-api#endpoints)
* Familiarity with `HTTP` & `JSON-RPC`
* Familiarity with the methods exposed by the blockchain you want to interact with such as [Bitcoin](/naas-api/bitcoin/), [Ethereum](/naas-api/ethereum) or any other of your choice

General information[​](/naas-api/#general-information "Direct link to General information")
-------------------------------------------------------------------------------------------

NaaS API is dedicated to developers who wish to integrate their applications with the various blockchains and their ecosystems.

The NaaS API facilitates interaction with nodes connected to different blockchains,
allowing access to on-chain data and enabling the transmission of transactions onto the network.

### JSON-RPC Standard[​](/naas-api/#json-rpc-standard "Direct link to JSON-RPC Standard")

The NaaS API operates on the JSON-RPC protocol.
JSON-RPC is a lightweight and stateless remote procedure call (RPC) protocol widely used in communicating with blockchain nodes.
All queries and responses in this API are formatted in JSON.

### Authentication & Security[​](/naas-api/#authentication--security "Direct link to Authentication & Security")

Depending on your preference, you can either utilize an `API key` or enhance security by combining an `API key with JWT` token.

For more details go to our [Authentication section](/naas-api/authentication).

**Best Practices**

* Never expose your `API key` in a client-side application or a public code repository. Always keep it securely on your server.
* Always communicate with the CoinAPI NaaS API over `HTTPS` (SSL/TLS) to encrypt data transmitted between your application and CoinAPI's servers
* When possible, avoid sending personally identifiable information (PII)
* Monitor for updates as our API can evolve, regularly check for updates to ensure compatibility

danger

Once your API key falls into the wrong hands, it can be used to make requests within your subscription.

danger

info

If your key has been compromised, you have the option to delete it at any time and generate a new one

info

### Limits[​](/naas-api/#limits "Direct link to Limits")

Your Subscription might have rate limits in place.
Ensure you're making requests within the allowed limits to avoid being interruption in access.

### Http Status Codes[​](/naas-api/#http-status-codes "Direct link to Http Status Codes")

* When the status code is not `200`, it indicates a lack of response from the node.
* Even if a `200` status code is received, there may still be a JSON-RPC error at the node level.
* A status code different from `200` implies that the response is not a JSON-RPC response.

#### Successful JSON-RPC Responses[​](/naas-api/#successful-json-rpc-responses "Direct link to Successful JSON-RPC Responses")

**200 OK**, valid response:

```
{  
    "jsonrpc": "2.0",  
    "id": "tracking-id-001",  
    "result": "0x11baedc"  
}
```

#### JSON-RPC Error Responses[​](/naas-api/#json-rpc-error-responses "Direct link to JSON-RPC Error Responses")

**200 OK**, includes error code from the node:

```
{  
    "jsonrpc": "2.0",  
    "id": "tracking-id-001",  
    "error": {  
        "code": -32602,  
        "message": "too many arguments, want at most 0"  
    }  
}
```

#### Non-JSON-RPC Error Responses (other than 200)[​](/naas-api/#non-json-rpc-error-responses-other-than-200 "Direct link to Non-JSON-RPC Error Responses (other than 200)")

**401**, unauthorized:

```
{  
    "error": "Invalid API key"  
}
```

Possible HTTP status codes and their meaning are listed below:

| Status Code | Meaning |
| --- | --- |
| 200 | Your request has been successfully processed by the server. However, it's essential to examine the response data as there might be JSON-RPC errors within the node's response. |
| 400 | Your request is malformed or contains incorrect parameters. There is an issue with the request itself. |
| 401 | Your request lacks proper authentication. It is typically due to an incorrect API key. |
| 403 | Your API key lacks the necessary permissions to access the requested resource. |
| 429 | Your request has exceeded the rate limits associated with your API key. |
| 550 | Server cannot provide the requested data at the moment. This may occur when requesting specific single items that are temporarily unavailable. |

### Making API Calls[​](/naas-api/#making-api-calls "Direct link to Making API Calls")

Json-RPC provides a structured and straightforward approach to
sending and receiving data, making it accessible for developers
using a wide range of programming languages and tools.

**curl**

You can use the curl command-line tool to make requests.
Here's an example of how to make a POST request to the Ethereum JSON-RPC API using curl:

```
curl -X POST \  
  "https://ethereum-mainnet-geth-archive.node.coinapi.io?apiKey=YOUR_API_KEY" \  
  -H "Content-Type: application/json" \  
  -d '{  
    "jsonrpc": "2.0",  
    "method": "eth_getTransactionReceipt",  
    "params": ["0x2444a649cd7fcd50ccb8c52c4159515fdf311eeb5dc02cf1b2c397b833fde012"],  
    "id": 1  
  }'
```

**web3.js**

If you prefer to use `JavaScript` and the `web3.js` library to interact with NaaS API, you can make request like this:

```
const axios = require('axios');  
  
const url = 'https://ethereum-mainnet-geth-archive.node.coinapi.io?apiKey=YOUR_API_KEY';  
const data = {  
  jsonrpc: '2.0',  
  method: 'eth_getTransactionReceipt',  
  params: ['0x2444a649cd7fcd50ccb8c52c4159515fdf311eeb5dc02cf1b2c397b833fde012'],  
  id: 1,  
};  
  
axios.post(url, data, {  
  headers: {  
    'Content-Type': 'application/json',  
  },  
})  
  .then(response => {  
    console.log(response.data);  
  })  
  .catch(error => {  
    console.error(error);  
  });
```

**Python**

You can also use Python to make HTTP POST requests to the NaaS API using the requests library.
Here's an example:

```
import requests  
  
url = 'https://ethereum-mainnet-geth-archive.node.coinapi.io?apiKey=YOUR_API_KEY'  
data = {  
    'jsonrpc': '2.0',  
    'method': 'eth_getTransactionReceipt',  
    'params': ['0x2444a649cd7fcd50ccb8c52c4159515fdf311eeb5dc02cf1b2c397b833fde012'],  
    'id': 1,  
}  
  
headers = {'Content-Type': 'application/json'}  
  
response = requests.post(url, json=data, headers=headers)  
  
if response.status_code == 200:  
    result = response.json()  
    print(result)  
else:  
    print(f"Request failed with status code {response.status_code}")
```

### Batch requests | Multi-Call[​](/naas-api/#batch-requests--multi-call "Direct link to Batch requests | Multi-Call")

Multiple requests can be sent simultaneously in an array when using the NaaS API, allowing for efficient handling of multiple operations.
In such a scenario, each request within the array is processed before all the requests are returned.

When requests are sent in a batch, they will only be returned after every request has been processed.
This behavior is particularly useful when you need to perform multiple operations and want to wait for all of them to complete before proceeding.

**Example of a Batch Request**

```
[  
  {"jsonrpc": "2.0", "id": "tracking-id-001", "method": "eth_blockNumber", "params": []},  
  {"jsonrpc": "2.0", "id": "tracking-id-002", "method": "eth_chainId", "params": []}  
]
```

In this batch request, we have two distinct JSON-RPC requests bundled togethe:

* The first request, identified by `tracking-id-001` invokes the `eth_blockNumber`, aiming to retrieve the current block number.
* The second request, with the identifier `tracking-id-002` calls the `eth_chainId` to fetch the current chain ID.

**Response to the Batch Request**

```
[  
    {  
        "jsonrpc": "2.0",  
        "id": "tracking-id-001",  
        "result": "0x11bb158"  
    },  
    {  
        "jsonrpc": "2.0",  
        "id": "tracking-id-002",  
        "result": "0x1"  
    }  
]
```

### Data Streaming[​](/naas-api/#data-streaming "Direct link to Data Streaming")

TODO

### Support[​](/naas-api/#support "Direct link to Support")

If you encounter any issues or have further questions regarding the Ethereum API, please contact our support team at **[[email protected]](/cdn-cgi/l/email-protection#67141217170815132704080e0906170e490e08)**.

### Summary[​](/naas-api/#summary "Direct link to Summary")

With the NaaS API, you can fully leverage the potential of the different blockchains in your applications.
This documentation covers all the necessary information to start utilizing this API and creating innovative blockchain-based solutions.

---

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Next

Authentication](/naas-api/authentication)

* [Introduction](/naas-api/#introduction)
* [Technical design](/naas-api/#technical-design)
* [Essentials](/naas-api/#essentials)
* [Endpoints](/naas-api/#endpoints)
* [Getting started](/naas-api/#getting-started)
* [General information](/naas-api/#general-information)
  + [JSON-RPC Standard](/naas-api/#json-rpc-standard)
  + [Authentication & Security](/naas-api/#authentication--security)
  + [Limits](/naas-api/#limits)
  + [Http Status Codes](/naas-api/#http-status-codes)
  + [Making API Calls](/naas-api/#making-api-calls)
  + [Batch requests | Multi-Call](/naas-api/#batch-requests--multi-call)
  + [Data Streaming](/naas-api/#data-streaming)
  + [Support](/naas-api/#support)
  + [Summary](/naas-api/#summary)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.