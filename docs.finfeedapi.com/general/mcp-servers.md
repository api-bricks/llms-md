MCP Servers | FinFeedAPI.com Documentation




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

* MCP Servers

On this page

Model Context Protocol (MCP) Servers
====================================

Understanding MCP[​](/general/mcp-servers#understanding-mcp "Direct link to Understanding MCP")
-----------------------------------------------------------------------------------------------

Model Context Protocol (MCP) is a thin specification that layers **self-describing JSON-Schema "functions" over existing HTTP APIs.** Every endpoint—its path, parameters, authentication rules, and error codes—is published as a machine-readable contract so that autonomous agents (LLMs, bots, test harnesses) can discover, validate, and invoke real requests without any custom glue code.

### When and Where to Attach MCP[​](/general/mcp-servers#when-and-where-to-attach-mcp "Direct link to When and Where to Attach MCP")

You can think of the public MCP relays listed below as "drop-in adapters" that sit **between your application and the native API**:

* **Client-side consolidation** – Point your mobile app, backend service, or data-science notebook at a *single* MCP host instead of juggling many base URLs.
* **Server-side gateway** – Place MCP in front of private micro-services to expose them securely over JSON-RPC without rewriting any code.
* **Automation & CI/CD** – Use MCP with generic JSON-RPC tooling (e.g. `curl`, Postman, or WebSocket clients) to script repetitive operational tasks across different APIs.

### What You Can Achieve with MCP[​](/general/mcp-servers#what-you-can-achieve-with-mcp "Direct link to What You Can Achieve with MCP")

| Capability | How it Helps |
| --- | --- |
| **Self-describing functions** | Each endpoint is exposed as a JSON-Schema contract that an agent can introspect to build valid requests. |
| **Multi-service router** | Reach FinFeedAPI, CoinAPI, and future services through a single `/mcp` endpoint by changing the `server` parameter. |
| **Schema-level validation** | The relay checks your payload against the schema before forwarding it, catching mistakes early. |
| **Consistent auth** | Reuse your existing `X-APIKey` or bearer `Authorization` header—no new tokens required. |
| **Zero-day coverage** | New upstream routes appear automatically in the MCP manifest—no SDK updates needed. |
| **Unified observability** | Logs, metrics, and rate limits can be enforced once at the MCP layer instead of per-service. |

> **In short**: MCP lets you treat a heterogeneous fleet of APIs as a single, extensible RPC surface—simplifying integration, reducing boilerplate, and speeding up development cycles.

**Two endpoint variants are available for every service:**

* `/mcp` – implements **HTTP streaming** (bidirectional over a single request).
* `/sse` – implements **Server-Sent Events (SSE)** for one-way, event-driven updates.

Individual Server Endpoints[​](/general/mcp-servers#individual-server-endpoints "Direct link to Individual Server Endpoints")
-----------------------------------------------------------------------------------------------------------------------------

| Product | Upstream API Base | MCP (HTTP Streaming) | SSE (Server-Sent Events) |
| --- | --- | --- | --- |
| FinFeedAPI SEC API | <https://api.sec.finfeedapi.com> | <https://mcp.sec.finfeedapi.com/mcp> | <https://mcp-sse.sec.finfeedapi.com/sse> |
| FinFeedAPI Stock API | <https://api-historical.stock.finfeedapi.com> | <https://mcp-historical.stock.finfeedapi.com/mcp> | <https://mcp-sse-historical.stock.finfeedapi.com/sse> |
| FinFeedAPI FX Realtime API | <https://api-realtime.fx.finfeedapi.com> | <https://mcp-realtime.fx.finfeedapi.com/mcp> | <https://mcp-sse-realtime.fx.finfeedapi.com/sse> |
| FinFeedAPI FX Historical API | <https://api-historical.fx.finfeedapi.com> | <https://mcp-historical.fx.finfeedapi.com/mcp> | <https://mcp-sse-historical.fx.finfeedapi.com/sse> |
| CoinAPI Market Data API | <https://rest.coinapi.io> | <https://mcp.md.coinapi.io/mcp> | <https://mcp-sse.md.coinapi.io/sse> |
| CoinAPI Exchange Rates Realtime API | <https://api-realtime.exrates.coinapi.io> | <https://mcp-realtime.exrates.coinapi.io/mcp> | <https://mcp-sse-realtime.exrates.coinapi.io/sse> |
| CoinAPI Exchange Rates Historical API | <https://api-historical.exrates.coinapi.io> | <https://mcp-historical.exrates.coinapi.io/mcp> | <https://mcp-sse-historical.exrates.coinapi.io/sse> |
| CoinAPI Indexes API | <https://rest-api.indexes.coinapi.io> | <https://mcp.indexes.coinapi.io/mcp> | <https://mcp-sse.indexes.coinapi.io/sse> |

Composite Server Endpoint[​](/general/mcp-servers#composite-server-endpoint "Direct link to Composite Server Endpoint")
-----------------------------------------------------------------------------------------------------------------------

| Endpoint | Aggregated Servers |
| --- | --- |
| **<https://mcp.api.apibricks.io/mcp>** (HTTP Streaming) |  |
| **<https://mcp.api.apibricks.io/sse>** (SSE) | All of the individual servers listed above |

---

### Example client configuration[​](/general/mcp-servers#example-client-configuration "Direct link to Example client configuration")

Below is a minimal JSON example showing how an application might be configured to talk to these servers. Replace `<YOUR_API_KEY>` with the key issued for your account.

```
{  
  "FinFeedAPI-SEC": {  
    "url": "https://mcp.sec.finfeedapi.com/mcp",  
    "headers": {  
      "X-APIKey": "<YOUR_API_KEY>"  
    }  
  },  
  "FinFeedAPI-Stock": {  
    "url": "https://mcp-historical.stock.finfeedapi.com/mcp",  
    "headers": {  
      "X-APIKey": "<YOUR_API_KEY>"  
    }  
  },  
  "FinFeedAPI-FX-Realtime": {  
    "url": "https://mcp-realtime.fx.finfeedapi.com/mcp",  
    "headers": {  
      "X-APIKey": "<YOUR_API_KEY>"  
    }  
  },  
  "FinFeedAPI-FX-Historical": {  
    "url": "https://mcp-historical.fx.finfeedapi.com/mcp",  
    "headers": {  
      "X-APIKey": "<YOUR_API_KEY>"  
    }  
  },  
  "CoinAPI-Market-Data": {  
    "url": "https://mcp.md.coinapi.io/mcp",  
    "headers": {  
      "X-CoinAPI-Key": "<YOUR_API_KEY>"  
    }  
  }  
}
```

Or for the composite MCP:

```
{  
  "APIBRICKS_COMPOSITE": {  
    "url": "https://mcp.apibricks.io/mcp",  
    "headers": {  
      "X-APIKey": "<YOUR_API_KEY>"  
    }  
  }  
}
```

Feel free to adapt the format to your application's configuration system.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Account](/general/customer-portal/Account)[Next

Product Changelog](/general/changelog/)

* [Understanding MCP](/general/mcp-servers#understanding-mcp)
  + [When and Where to Attach MCP](/general/mcp-servers#when-and-where-to-attach-mcp)
  + [What You Can Achieve with MCP](/general/mcp-servers#what-you-can-achieve-with-mcp)
* [Individual Server Endpoints](/general/mcp-servers#individual-server-endpoints)
* [Composite Server Endpoint](/general/mcp-servers#composite-server-endpoint)
  + [Example client configuration](/general/mcp-servers#example-client-configuration)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.