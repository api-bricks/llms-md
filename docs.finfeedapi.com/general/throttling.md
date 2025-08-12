Throttling requests | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* Throttling

On this page

FinFeedAPI Throttling Process
=============================

Overview[​](/general/throttling#overview "Direct link to Overview")
-------------------------------------------------------------------

FinFeedAPI implements a sophisticated throttling process to ensure fair usage and protect our services from being overwhelmed by too many requests. This document outlines the key aspects of our throttling mechanism, focusing on rate limiting, quota management, and how these apply across our product suite.

Handling Throttling During Scaling[​](/general/throttling#handling-throttling-during-scaling "Direct link to Handling Throttling During Scaling")
-------------------------------------------------------------------------------------------------------------------------------------------------

While FinFeedAPI is scaling to meet your higher request rate, you may encounter throttling. Here's how to handle it:

1. **Implement Exponential Backoff**: When receiving a 429 error, use an exponential backoff strategy to retry the request.
2. **Monitor Error Rates**: Keep track of the 429 errors you receive and adjust your request rate accordingly.
3. **Distribute Requests**: Spread your requests evenly over time to avoid sudden spikes that may trigger throttling.

It's important to note that in the case of a 429 error, we will initiate scaling to accommodate your increased request rate. However, this scaling process, for both read and write operations, occurs gradually and is not instantaneous. During this scaling period, you may encounter 429 (Too Many Requests) errors. These errors will dissipate once the scaling is complete.

When you receive a 429 error, we will provide a `Retry-After` header in the response. This header contains the number of seconds you should wait before making another request. It's crucial to respect this value to avoid further throttling and to allow the scaling process to complete effectively.

Some endpoints are being scaled aggressively, which may prevent them from encountering a 429 error entirely. The behavior can vary between endpoints due to differences in infrastructure, data types, and load distribution.

Performance Considerations[​](/general/throttling#performance-considerations "Direct link to Performance Considerations")
-------------------------------------------------------------------------------------------------------------------------

### High-Volume Data Processing[​](/general/throttling#high-volume-data-processing "Direct link to High-Volume Data Processing")

Some applications using FinFeedAPI may need to process large volumes of data. These applications can achieve high transfer rates by:

* Utilizing powerful compute resources (e.g., high-performance cloud instances)
* Implementing efficient data processing algorithms
* Aggregating throughput across multiple instances for processing terabytes of data

### Latency-Sensitive Applications[​](/general/throttling#latency-sensitive-applications "Direct link to Latency-Sensitive Applications")

For applications requiring low-latency responses, such as real-time trading platforms:

* FinFeedAPI aims to provide consistent latencies of approximately 100-200 milliseconds for small data requests
* Larger data requests may have slightly higher latencies, but with quick first-byte-out times

### Accelerating Performance[​](/general/throttling#accelerating-performance "Direct link to Accelerating Performance")

To further enhance performance for specific use cases:

1. **Content Delivery Networks (CDNs)**: Implement a CDN to cache frequently accessed data closer to your users.
2. **In-Memory Caching**: Use in-memory caching solutions to reduce latency for frequently accessed data.
3. **Optimized Network Routes**: Consider using services that optimize data transfer over long distances if your application is geographically distributed.

Best Practices for Optimizing FinFeedAPI Performance[​](/general/throttling#best-practices-for-optimizing-finfeedapi-performance "Direct link to Best Practices for Optimizing FinFeedAPI Performance")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Efficient Data Retrieval**: Request only the data you need by using appropriate API endpoints and query parameters.
2. **Compression**: Enable compression in your API requests to reduce data transfer sizes.
3. **Connection Reuse**: Implement connection pooling in your application to reuse HTTP connections.
4. **Asynchronous Processing**: Use asynchronous programming techniques to handle multiple API requests efficiently.
5. **Error Handling**: Implement robust error handling and retry mechanisms to manage temporary service disruptions.

By following these guidelines and best practices, you can optimize your application's performance when using FinFeedAPI, ensuring efficient data retrieval and processing even at high volumes.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Security and Compliance](/general/security)[Next

Usage Credits](/general/usage-credits)

* [Overview](/general/throttling#overview)
* [Handling Throttling During Scaling](/general/throttling#handling-throttling-during-scaling)
* [Performance Considerations](/general/throttling#performance-considerations)
  + [High-Volume Data Processing](/general/throttling#high-volume-data-processing)
  + [Latency-Sensitive Applications](/general/throttling#latency-sensitive-applications)
  + [Accelerating Performance](/general/throttling#accelerating-performance)
* [Best Practices for Optimizing FinFeedAPI Performance](/general/throttling#best-practices-for-optimizing-finfeedapi-performance)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.