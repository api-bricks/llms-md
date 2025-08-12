API limits and billing metrics | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/naas-api/api-limits-and-billing-metrics)

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

* API limits and billing

On this page

API limits and billing metrics
==============================

API limits are a crucial aspect of any API product, and they exist for several important reasons. They are designed to ensure fair usage and maintain the quality of service for all users.
By implementing these limits, we can prevent any single user from overloading the system, which could potentially degrade the performance for others.
This is a standard practice across the industry and is essential for maintaining a high level of service.

One of the key limits we have in place is the Concurrency limit. This limit is specifically designed to protect our infrastructure.
It controls the number of simultaneous API calls/requests that can be executed at any given moment.
Each API call/request increases the Concurrency limit against your quota, and it decreases when the call/request finishes.
This ensures that our servers are not overwhelmed by too many simultaneous requests, thereby ensuring smooth and efficient operation.

The specific limits that apply to you depend on several factors. These include the plan you have subscribed to, the product you are using, and the protocol you are utilizing.
Different products and protocols may have different limits, reflecting their varying requirements and capabilities.

We understand that different users may have different needs, and we try to accommodate these requests whenever possible.
Therefore, some limits, such as the Concurrency limit, can be requested to be increased through our support team.
We review these requests on a case-by-case basis, taking into account factors such as your usage history and the capacity of our infrastructure.

There are also limits that depend on your plan, such as the Request limit or the Node as a Service units limit.
If you exceed these limits, you can continue to use our services by paying an overage fee. This allows us to maintain a high level of service for all users, even during periods of high demand.

In conclusion, API limits are a necessary and important part of our service.
They ensure that all users can enjoy a high-quality, reliable service, and they protect our infrastructure from being overwhelmed.

Limits applied to our products[​](/naas-api/api-limits-and-billing-metrics#limits-applied-to-our-products "Direct link to Limits applied to our products")
----------------------------------------------------------------------------------------------------------------------------------------------------------

| Product name | Limits |
| --- | --- |
| NAAS REST API | NAAS Credits Limit NAAS Concurrency Limit |
| NAAS WebSocket API | NAAS Credits Limit  NAAS Concurrency Limit |

Multiple API keys for a subscription[​](/naas-api/api-limits-and-billing-metrics#multiple-api-keys-for-a-subscription "Direct link to Multiple API keys for a subscription")
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

At CoinAPI, we understand that our customers may have diverse needs and may require multiple API keys for a single subscription.
We have designed our system to accommodate this requirement, allowing you to add additional API keys to your subscription. These keys operate within the confines of a single limit,
ensuring that you have the flexibility you need without compromising on control.

Each API key can be further customized with a more precise limit. This feature allows you to manage your usage effectively,
ensuring that each key is used optimally and within its designated limit. This level of control can be particularly useful in managing resources and preventing overuse.

In addition to these features, we also offer the ability for API calls using a specific API key to generate overage, i.e., exceed the quota.
This can be particularly useful in situations where you anticipate a higher volume of calls. However, it's important to note that if the limit is exceeded,
the API calls may be rejected to prevent overuse and maintain system integrity.
All these settings, including the limits and the ability to set overage, can be managed from the Customer Portal.
This ensures that you have complete control over your subscription and can make adjustments as and when needed.

### Customizing Limits for API Keys within a Subscription[​](/naas-api/api-limits-and-billing-metrics#customizing-limits-for-api-keys-within-a-subscription "Direct link to Customizing Limits for API Keys within a Subscription")

If both API keys, each with a limit of 500, exhaust their allotted limits, reaching a combined total of 1000, further requests made using either key will be rejected until the limit resets.
This ensures that the total usage across all keys within the subscription does not exceed the subscription limit.

### Exceeding Limits for API Keys within a Subscription[​](/naas-api/api-limits-and-billing-metrics#exceeding-limits-for-api-keys-within-a-subscription "Direct link to Exceeding Limits for API Keys within a Subscription")

If one API key within the subscription exceeds its limit of 500, while the other key is still within its limit, requests made using the exceeded key will be
rejected until the limit resets. However, requests made using the other key, which is still within its limit, will continue to be processed without interruption.

info

In summary, managing limits within a subscription involves ensuring that the usage across all API keys and services remains within the specified limits,
with mechanisms in place to handle potential overages and maintain service availability and quality.

Node as a Service API[​](/naas-api/api-limits-and-billing-metrics#node-as-a-service-api "Direct link to Node as a Service API")
-------------------------------------------------------------------------------------------------------------------------------

The utilization of CoinAPI.io's API is quantified in API Credits, providing a standardized measure for usage. Each API Credit value is assigned based on the complexity and resource intensity of specific methods within the platform. The credit values range from 10 to 500, with each method having a distinct credit value.

For instance, `eth_call` is assigned a value of 20 API Credits. These credit values take into account various intricate factors such as computational load, memory consumption, disk usage, and network resources associated with the execution of each method.

This dynamic credit system ensures a fair and accurate representation of the resources utilized by different API methods, offering transparency and flexibility in aligning with CoinAPI.io's pricing plans.

### Request limit / APIKey[​](/naas-api/api-limits-and-billing-metrics#request-limit--apikey "Direct link to Request limit / APIKey")

```
X-UnitsLimit-Quota-Overage: disabled  
X-UnitsLimit-Quota-Allocated: 10000000  
X-UnitsLimit-Used: 0  
X-UnitsLimit-Quota-Remaining: 10000000
```

| HTTP Header | Type | Description |
| --- | --- | --- |
| X-UnitsLimit-Quota-Overage | string | Provides information about whether a given API key may exceed the plan quota within a 24-hour time frame, which could result in additional charges. This header is fully defined and configured in the customer portal. |
| X-UnitsLimit-Quota-Allocated | string | Total number of requests that can be made within a specific subscription during a 24-hour time frame. This quota allocation is determined based on the user's subscription purchase. |
| X-UnitsLimit-Quota-Remaining | string | Provides valuable information about the remaining quota within the subscription for making requests within a 24-hour time frame. This header indicates the number of requests that can still be made within the allocated quota for the current 24-hour period. |
| X-UnitsLimit-Used | int | Provides information about the request limit that has been used within the last 24-hour period. This header indicates the amount of request capacity consumed based on the usage history. It is important to note that the header is not always appended to every request to optimize the operation of the API. |

* Bitcoin
* Ethereum

| Method name | Value |
| --- | --- |
| abandontransaction | 10 |
| abortrescan | 10 |
| addnode | 10 |
| analyzepsbt | 10 |
| bumpfee | 10 |
| combinepsbt | 10 |
| combinerawtransaction | 10 |
| createmultisig | 10 |
| createpsbt | 10 |
| createrawtransaction | 10 |
| createwallet | 10 |
| decoderawtransaction | 10 |
| decodepsbt | 10 |
| decodescript | 10 |
| deriveaddresses | 10 |
| disconnectnode | 10 |
| dumpprivkey | 10 |
| estimatesmartfee | 10 |
| finalizepsbt | 10 |
| fundrawtransaction | 10 |
| generateblock | 10 |
| generatetoaddress | 10 |
| generatetodescriptor | 10 |
| getaddressesbylabel | 10 |
| getbalance | 10 |
| getbalances | 10 |
| getbestblockhash | 10 |
| getblock | 10 |
| getblockchaininfo | 10 |
| getblockcount | 10 |
| getblockfilter | 10 |
| getblockhash | 10 |
| getblockheader | 10 |
| getblockstats | 10 |
| getblocktemplate | 10 |
| getchaintips | 10 |
| getchaintxstats | 10 |
| getconnectioncount | 10 |
| getdifficulty | 10 |
| getindexinfo | 10 |
| getmemoryinfo | 10 |
| getmempoolancestors | 10 |
| getmempooldescendants | 10 |
| getmempoolentry | 10 |
| getmempoolinfo | 10 |
| getmininginfo | 10 |
| getnettotals | 10 |
| getnetworkhashps | 10 |
| getnetworkinfo | 10 |
| getnewaddress | 10 |
| getnodeaddresses | 10 |
| getpeerinfo | 10 |
| getrawchangeaddress | 10 |
| getrawmempool | 10 |
| getrawtransaction | 10 |
| getreceivedbyaddress | 10 |
| getreceivedbylabel | 10 |
| getrpcinfo | 10 |
| gettransaction | 10 |
| gettxout | 10 |
| gettxoutproof | 10 |
| gettxoutsetinfo | 10 |
| help | 10 |
| importaddress | 10 |
| importdescriptors | 10 |
| importmulti | 10 |
| importprivkey | 10 |
| importprunedfunds | 10 |
| importpubkey | 10 |
| importwallet | 10 |
| keypoolrefill | 10 |
| listreceivedbyaddress | 10 |
| listaddressgroupings | 10 |
| listbanned | 10 |
| listlabels | 10 |
| listlockunspent | 10 |
| listsinceblock | 10 |
| listtransactions | 10 |

| Method name | Value |
| --- | --- |
| eth\_blockNumber | 20 |
| eth\_call | 20 |
| eth\_chainId | 20 |
| eth\_coinbase | 20 |
| eth\_createAccessList | 20 |
| eth\_estimateGas | 20 |
| eth\_feeHistory | 20 |
| eth\_gasPrice | 20 |
| eth\_getBalance | 20 |
| eth\_getBlockByHash | 20 |
| eth\_getBlockByNumber | 20 |
| eth\_getBlockReceipts | 20 |
| eth\_getBlockTransactionCountByHash | 20 |
| eth\_getBlockTransactionCountByNumber | 20 |
| eth\_getCode | 20 |
| eth\_getFilterChanges | 20 |
| eth\_getFilterLogs | 20 |
| eth\_getLogs | 20 |
| eth\_getProof | 20 |
| eth\_getStorageAt | 20 |
| eth\_getTransactionByBlockHashAndIndex | 20 |
| eth\_getTransactionByBlockNumberAndIndex | 20 |
| eth\_getTransactionByHash | 20 |
| eth\_getTransactionCount | 20 |
| eth\_getTransactionReceipt | 20 |
| eth\_getUncleByBlockHashAndIndex | 20 |
| eth\_getUncleByBlockNumberAndIndex | 20 |
| eth\_getUncleCountByBlockHash | 20 |
| eth\_getUncleCountByBlockNumber | 20 |
| eth\_getWork | 20 |
| eth\_hashrate | 20 |
| eth\_maxPriorityFeePerGas | 20 |
| eth\_mining | 20 |
| eth\_newBlockFilter | 20 |
| eth\_newFilter | 20 |
| eth\_newPendingTransactionFilter | 20 |
| eth\_protocolVersion | 20 |
| eth\_sendRawTransaction | 20 |
| eth\_sign | 20 |
| eth\_signTransaction | 20 |
| eth\_submitWork | 20 |
| eth\_subscribe | 20 |
| eth\_subscribePendingTransactions | 20 |
| eth\_syncing | 20 |
| eth\_uninstallFilter | 20 |
| eth\_unsubscribe | 20 |
| getBeaconBlocksAttestations | 20 |
| getBlockByRoot | 20 |
| getTxPoolStatus | 20 |
| net\_listening | 20 |
| net\_peerCount | 20 |
| net\_version | 20 |
| trace\_block | 70 |
| trace\_call | 70 |
| trace\_callMany | 70 |
| trace\_filter | 70 |
| trace\_rawTransaction | 70 |
| trace\_replayBlockTransactions | 500 |
| trace\_replayTransaction | 500 |
| trace\_transaction | 70 |
| txpool\_content | 500 |
| txpool\_contentFrom | 70 |
| txpool\_inspect | 70 |
| web3\_clientVersion | 20 |
| web3\_sha3 | 20 |

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Authentication](/naas-api/authentication)[Next

Bitcoin](/naas-api/bitcoin/)

* [Limits applied to our products](/naas-api/api-limits-and-billing-metrics#limits-applied-to-our-products)
* [Multiple API keys for a subscription](/naas-api/api-limits-and-billing-metrics#multiple-api-keys-for-a-subscription)
  + [Customizing Limits for API Keys within a Subscription](/naas-api/api-limits-and-billing-metrics#customizing-limits-for-api-keys-within-a-subscription)
  + [Exceeding Limits for API Keys within a Subscription](/naas-api/api-limits-and-billing-metrics#exceeding-limits-for-api-keys-within-a-subscription)
* [Node as a Service API](/naas-api/api-limits-and-billing-metrics#node-as-a-service-api)
  + [Request limit / APIKey](/naas-api/api-limits-and-billing-metrics#request-limit--apikey)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.