CoinAPI API Performance Testing Guide | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/market-data/performance-testing-guide)

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

* Performance Testing Guide

On this page

CoinAPI API Performance Testing Guide
=====================================

This guide provides detailed steps to test the performance of the CoinAPI API across REST, WebSocket, and FIX interfaces. It's designed to help you efficiently measure and analyze the API's performance.

1. REST API Performance Testing[​](/market-data/performance-testing-guide#1-rest-api-performance-testing "Direct link to 1. REST API Performance Testing")
----------------------------------------------------------------------------------------------------------------------------------------------------------

Test the latency of API requests using curl commands on Linux.

### Example Command[​](/market-data/performance-testing-guide#example-command "Direct link to Example Command")

```
cat > curl-format.txt << EOF  
    time_namelookup:  %{time_namelookup}s\n  
    time_connect:  %{time_connect}s\n  
    time_appconnect:  %{time_appconnect}s\n  
    time_pretransfer:  %{time_pretransfer}s\n  
    time_redirect:  %{time_redirect}s\n  
    time_starttransfer:  %{time_starttransfer}s\n  
    ----------  
    time_total:  %{time_total}s\n  
EOF  
curl --http2-prior-knowledge -w "@curl-format.txt" -o /dev/null -s "https://rest.coinapi.io/"
```

2. WebSocket API Performance Testing[​](/market-data/performance-testing-guide#2-websocket-api-performance-testing "Direct link to 2. WebSocket API Performance Testing")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The WebSocket client application is designed for subscribing to data from our WebSocket service, capturing metrics such as message counts and latency.

**Note**: This application is not intended to subscribe to all data feeds simultaneously as it uses only one connection. To effectively monitor various data types, consider creating multiple instances or using separate connections for each subscription type.

### Compilation and Running[​](/market-data/performance-testing-guide#compilation-and-running "Direct link to Compilation and Running")

1. Ensure .NET 8.0 or higher is installed.
2. Navigate to the project directory and compile the application using `dotnet build`.
3. Run the application with `dotnet run` and specify your parameters.

For more details, visit the [WebSocket Client Application Repository](https://github.com/api-bricks/api-bricks-sdk/tree/master/coinapi/market-data-api-ws/csharp-ws/sdk/CoinAPI.WebSocket.Stats.Console).

3. FIX Protocol Testing[​](/market-data/performance-testing-guide#3-fix-protocol-testing "Direct link to 3. FIX Protocol Testing")
----------------------------------------------------------------------------------------------------------------------------------

The FIX client enables session management, data subscription, and message processing using the QuickFix engine.

### Compilation and Running[​](/market-data/performance-testing-guide#compilation-and-running-1 "Direct link to Compilation and Running")

1. Update `config_nossl.cfg` with your session settings.
2. Compile the application with `dotnet build` in the project directory.
3. Execute the compiled application to start your testing session.

Access the complete source code and setup instructions at the [FIX Client Application Repository](https://github.com/api-bricks/api-bricks-sdk/tree/master/coinapi/market-data-api-fix/sdk/csharp-fix-v2).

Good Practices for Performance Testing[​](/market-data/performance-testing-guide#good-practices-for-performance-testing "Direct link to Good Practices for Performance Testing")
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Incorporating good practices into your testing strategy can significantly improve the reliability and efficiency of your performance testing. Here are some recommendations:

1. **Efficient Message Handling**: Fetch messages from the connection as swiftly as possible and process them in a separate thread. This separation ensures that message retrieval is not bottlenecked by processing time.
2. **Monitoring and Separation**: Keep a count of messages and manage their queue separately. This practice helps in isolating the fetching mechanism from the consumption process, allowing for more accurate performance measurements and streamlined processing.
3. **Utilize Multithreading Wisely**: When employing multithreading, consider establishing multiple connections to distribute the load effectively. This approach can enhance throughput by leveraging parallel processing, especially in high-demand scenarios.

### Very Important[​](/market-data/performance-testing-guide#very-important "Direct link to Very Important")

**If latency increases, it is necessary to split data acquisition across multiple connections to utilize more threads effectively.**

By adhering to these practices, including the emphasized point on managing increasing latency through distributed data acquisition, you can ensure a more robust and efficient performance testing process.

---

This guide aims to streamline your API performance testing across different interfaces. For further assistance, refer to the detailed documentation provided in the links above.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Retrieve and analyze crypto order book data using a cryptocurrency API](/market-data/how-to-guides/retrieve-and-analyze-crypto-order-book-data-using-a-cryptocurrency-API)

* [1. REST API Performance Testing](/market-data/performance-testing-guide#1-rest-api-performance-testing)
  + [Example Command](/market-data/performance-testing-guide#example-command)
* [2. WebSocket API Performance Testing](/market-data/performance-testing-guide#2-websocket-api-performance-testing)
  + [Compilation and Running](/market-data/performance-testing-guide#compilation-and-running)
* [3. FIX Protocol Testing](/market-data/performance-testing-guide#3-fix-protocol-testing)
  + [Compilation and Running](/market-data/performance-testing-guide#compilation-and-running-1)
* [Good Practices for Performance Testing](/market-data/performance-testing-guide#good-practices-for-performance-testing)
  + [Very Important](/market-data/performance-testing-guide#very-important)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.