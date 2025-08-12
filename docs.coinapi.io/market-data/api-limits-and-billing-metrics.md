API limits and billing metrics | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/api-limits-and-billing-metrics)

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
* [Performance Testing Guide](/market-data/performance-testing-guide)

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

Limits applied to our products[​](/market-data/api-limits-and-billing-metrics#limits-applied-to-our-products "Direct link to Limits applied to our products")
-------------------------------------------------------------------------------------------------------------------------------------------------------------

| Product name | Limits |
| --- | --- |
| Market Data REST API | Credits Limit Concurrency Limit |
| Market Data WebSocket API | Request Limit / IP Hello Limit / IP Concurrency limit / APIKey |
| Market Data FIX API | Session / APIKey  Each API Key can have one session, and when next session is stablished then current is disconnected |
| Market Data S3 API | TODO |

Multiple API keys for a subscription[​](/market-data/api-limits-and-billing-metrics#multiple-api-keys-for-a-subscription "Direct link to Multiple API keys for a subscription")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

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

### Customizing Limits for API Keys within a Subscription[​](/market-data/api-limits-and-billing-metrics#customizing-limits-for-api-keys-within-a-subscription "Direct link to Customizing Limits for API Keys within a Subscription")

If both API keys, each with a limit of 500, exhaust their allotted limits, reaching a combined total of 1000, further requests made using either key will be rejected until the limit resets.
This ensures that the total usage across all keys within the subscription does not exceed the subscription limit.

### Exceeding Limits for API Keys within a Subscription[​](/market-data/api-limits-and-billing-metrics#exceeding-limits-for-api-keys-within-a-subscription "Direct link to Exceeding Limits for API Keys within a Subscription")

If one API key within the subscription exceeds its limit of 500, while the other key is still within its limit, requests made using the exceeded key will be
rejected until the limit resets. However, requests made using the other key, which is still within its limit, will continue to be processed without interruption.

info

In summary, managing limits within a subscription involves ensuring that the usage across all API keys and services remains within the specified limits,
with mechanisms in place to handle potential overages and maintain service availability and quality.

Market Data / REST API[​](/market-data/api-limits-and-billing-metrics#market-data--rest-api "Direct link to Market Data / REST API")
------------------------------------------------------------------------------------------------------------------------------------

Any authenticated endpoint is providing (in HTTP response headers) information about the current state of the limits associated with API Key. In this section we will describe each limit.

### Request limit / APIKey[​](/market-data/api-limits-and-billing-metrics#request-limit--apikey "Direct link to Request limit / APIKey")

```
X-RateLimit-Limit: 1000000  
X-RateLimit-Remaining: 999989  
X-RateLimit-Request-Cost: 1  
X-RateLimit-Reset: 2018-01-22T15:25:15.1234567Z
```

The request limit define number of maximum requests that could be executed in the 24 hours period (sliding/rollowing window - always last 24 hours from specific moment) for your subscription.

We define 'request' as the amount of data you're asking for. This isn't always the same as the number of times you call the API. If you're not using a 'limit' parameter in your API call, or if it's not available, then each API call you make is counted as one request. However, if you are using a 'limit' parameter, then it works a bit differently. In this case, every 100 pieces of data you ask for is counted as one request. So, if you ask for 200 pieces of data in one API call, that would be counted as two requests.

In the given example:
The allocated quota (X-RateLimit-Limit) is the total number of requests that you're allowed to make in 24 hours. This number is set based on your subscription level.
The request costs (X-RateLimit-Request-Cost) are the number of requests that you've already made within the current 24-hour period. Each API call you make has a cost associated with it, and these costs add up over time.
The remaining requests (X-RateLimit-Remaining) are calculated by subtracting the sum of the request costs from the allocated quota. This tells you how many more requests you can make within the current 24-hour period. So in the example given, at 13:00 UTC on 2019-08-22, the number of remaining requests would be equal to the allocated quota, minus the sum of all the request costs that have been incurred from 13:00 UTC on 2019-08-21 to 13:00 UTC on 2019-08-22.

| HTTP Header | Type | Description |
| --- | --- | --- |
| X-RateLimit-Used | int | Provides information about the request limit that has been used within the last 24-hour period. This header indicates the amount of request capacity consumed based on the usage history. It is important to note that the header is not always appended to every request to optimize the operation of the API. |
| X-RateLimit-Limit | int | Is an optional feature that can be enabled via the customer portal to impose a limit on the capabilities of a specific API key. It allows you to define a threshold for the number of requests that can be made using a single API key within a 24-hour time frame. |
| X-RateLimit-Remaining | int | Provides information about the number of requests that can still be made, based on the 24-hour usage history. This header serves as a helpful indicator of the remaining request capacity, allowing API consumers to manage their usage effectively. It is important to note that the header is not always appended to every request to optimize the operation of the API. |
| X-RateLimit-Request-Cost | int | The number of requests used to generate current HTTP response. |
| X-RateLimit-Reset | timestring | The time when all provisioned requests are available to execute again if no more requests will be executed. |
| X-RateLimit-Quota-Overage | string | Provides information about whether a given API key may exceed the plan quota within a 24-hour time frame, which could result in additional charges. This header is fully defined and configured in the customer portal. |
| X-RateLimit-Quota-Allocated | uint64 | Total number of requests that can be made within a specific subscription during a 24-hour time frame. This quota allocation is determined based on the user's subscription purchase. |
| X-RateLimit-Quota-Remaining | int64 | Provides valuable information about the remaining quota within the subscription for making requests within a 24-hour time frame. This header indicates the number of requests that can still be made within the allocated quota for the current 24-hour period. |

```
GET v1/exchanges/ECB/apiKey-ED802AF4-E855-YOUR-API-KEY  
Host: coinapi.io  
X-RateLimit-Used: 1000  
X-RateLimit-Limit: 5000  
X-RateLimit-Remaining: 4000  
X-RateLimit-Request-Cost: 1  
X-RateLimit-Reset: 2023-05-05T12:00:00.0000001Z  
X-RateLimit-Quota-Overage: ENABLED  
X-RateLimit-Quota-Allocated: 10000  
X-RateLimit-Quota-Remaining: 5000
```

Explanation:

* X-RateLimit-Used: 1000 (requests used in the last 24 hours)
* X-RateLimit-Limit: 5000 (total request limit within a 24-hour time frame)
* X-RateLimit-Remaining: 4000 (requests remaining within the last 24 hours)
* X-RateLimit-Request-Cost: 1 (cost or "weight" of each individual request)
* X-RateLimit-Reset: 2023-05-05T12:00:00.0000001Z (when the rate limit will reset within a 24-hour period)
* X-RateLimit-Overage: ENABLED (API key may exceed the plan quota within a 24-hour time frame)
* X-RateLimit-Quota-Allocated: 10000 (total number of requests allowed for all API keys within the subscription within a 24-hour time frame)
* X-RateLimit-Quota-Remaining: 5000 (requests remaining within the subscription's allocated quota within the last 24 hours)

### Concurrency limit / APIKey[​](/market-data/api-limits-and-billing-metrics#concurrency-limit--apikey "Direct link to Concurrency limit / APIKey")

```
X-ConcurrencyLimit-Limit: 10  
X-ConcurrencyLimit-Remaining: 5
```

The concurrency limit defines the number of maximum concurrent API calls/requests that the API could process for your subscription at the current moment. Every API call/request increases the Concurrency limit against quota, and when it finishes, decreases it.

| HTTP Header | Type | Description |
| --- | --- | --- |
| X-ConcurrencyLimit-Limit | int | Concurrency limit allocated for your API key. |
| X-ConcurrencyLimit-Remaining | int | The number of concurrent API calls/requests available to be executed in this moment for your API key. |

Market Data / WebSocket API[​](/market-data/api-limits-and-billing-metrics#market-data--websocket-api "Direct link to Market Data / WebSocket API")
---------------------------------------------------------------------------------------------------------------------------------------------------

API access is subject to limits and n this section we will describe each limit.

### Request limit / IP[​](/market-data/api-limits-and-billing-metrics#request-limit--ip "Direct link to Request limit / IP")

```
X-WsRequestsPerIpLimit-Limit: 10  
X-WsRequestsPerIpLimit-WindowSizeMs: 10000  
X-WsRequestsPerIpLimit-Remaining: 0  
X-WsRequestsPerIpLimit-RetryAfterMs: 564
```

We define WebSocket request as the event when the WebSocket upgrade on the HTTP is happening. The request limit restricts the number of maximum allowed newly initiated WebSocket connections per IP address in a time interval (sliding/rolling window ending at a specific moment) for your subscription. Limit prevents your client application from abusing the API by reconnecting in the loop without exponential backoff.

| HTTP Header | Type | Description |
| --- | --- | --- |
| X-WsRequestsPerIpLimit-Limit | int | Value of the limit quota allocated. |
| X-WsRequestsPerIpLimit-Remaining | int | Value of the limit quota left at the moment, counted from last WindowSizeMs milliseconds. |
| X-WsRequestsPerIpLimit-WindowSizeMs | int | Window size on which the remaining value was calculated in milliseconds. |
| X-WsRequestsPerIpLimit-RetryAfterMs | int | The number of milliseconds after which Remaining > 0. *(exist only in case of the error)* |

### Hello limit / IP[​](/market-data/api-limits-and-billing-metrics#hello-limit--ip "Direct link to Hello limit / IP")

```
X-WsHelloPerIpLimit-Limit: 10  
X-WsHelloPerIpLimit-WindowSizeMs: 10000  
X-WsHelloPerIpLimit-Remaining: 0  
X-WsHelloPerIpLimit-RetryAfterMs: 564
```

The hello limit restricts the number of maximum allowed hello messages per IP address in the time interval (sliding/rolling window ending at a specific moment) for your subscription. Limit prevents your client application from abusing the API by changing the scope of the subscription.

| HTTP Header | Type | Description |
| --- | --- | --- |
| X-WsHelloPerIpLimit-Limit | int | Value of the limit quota allocated. |
| X-WsHelloPerIpLimit-Remaining | int | Value of the limit quota left at the moment, counted from last WindowSizeMs milliseconds. |
| X-WsHelloPerIpLimit-WindowSizeMs | int | Window size on which the remaining value was calculated in milliseconds. |
| X-WsHelloPerIpLimit-RetryAfterMs | int | The number of milliseconds after which Remaining > 0. *(exist only in case of the error)* |

### Concurrency limit / APIKey[​](/market-data/api-limits-and-billing-metrics#concurrency-limit--apikey-1 "Direct link to Concurrency limit / APIKey")

```
X-ConcurrencyLimit-Limit: 10  
X-ConcurrencyLimit-Remaining: 5
```

The concurrency limit defines the number of maximum allowed concurrent websocket connections per APIKey at the current moment. Every new WebSocket connection increases the Concurrency limit against quota, and when it's closed, decreases it.

| HTTP Header | Type | Description |
| --- | --- | --- |
| X-ConcurrencyLimit-Limit | int | Concurrency limit allocated for your API key. |
| X-ConcurrencyLimit-Remaining | int | The number of concurrent WebSocket connections available to be established in this moment for your API key. |

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Authentication](/market-data/authentication)[Next

Introduction](/market-data/metadata-tables/introduction)

* [Limits applied to our products](/market-data/api-limits-and-billing-metrics#limits-applied-to-our-products)
* [Multiple API keys for a subscription](/market-data/api-limits-and-billing-metrics#multiple-api-keys-for-a-subscription)
  + [Customizing Limits for API Keys within a Subscription](/market-data/api-limits-and-billing-metrics#customizing-limits-for-api-keys-within-a-subscription)
  + [Exceeding Limits for API Keys within a Subscription](/market-data/api-limits-and-billing-metrics#exceeding-limits-for-api-keys-within-a-subscription)
* [Market Data / REST API](/market-data/api-limits-and-billing-metrics#market-data--rest-api)
  + [Request limit / APIKey](/market-data/api-limits-and-billing-metrics#request-limit--apikey)
  + [Concurrency limit / APIKey](/market-data/api-limits-and-billing-metrics#concurrency-limit--apikey)
* [Market Data / WebSocket API](/market-data/api-limits-and-billing-metrics#market-data--websocket-api)
  + [Request limit / IP](/market-data/api-limits-and-billing-metrics#request-limit--ip)
  + [Hello limit / IP](/market-data/api-limits-and-billing-metrics#hello-limit--ip)
  + [Concurrency limit / APIKey](/market-data/api-limits-and-billing-metrics#concurrency-limit--apikey-1)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.