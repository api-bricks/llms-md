Authentication Process | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/authentication)

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

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [FAQ](/general/faq/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* Authentication

On this page

CoinAPI Authorization Process
=============================

Overview[​](/general/authentication#overview "Direct link to Overview")
-----------------------------------------------------------------------

CoinAPI offers a range of products and services for cryptocurrency data and trading. Our sophisticated authorization process ensures secure and fair access across all CoinAPI products, including but not limited to market data, trading APIs, and analytics tools. This document outlines the key aspects of our authorization flow, focusing on quota management, pay-as-you-go functionality, and advanced authentication methods that apply uniformly across our product suite.

Authorization Flow[​](/general/authentication#authorization-flow "Direct link to Authorization Flow")
-----------------------------------------------------------------------------------------------------

1. **API Key Validation**
2. **Organization Validation**
3. **JWT Token Processing** (if applicable)
4. **Spend Management checks**
5. **Quota Checks and Pay-As-You-Go Handling**

### 1. API Key Validation[​](/general/authentication#1-api-key-validation "Direct link to 1. API Key Validation")

We verify the API key's validity and its association with the requested CoinAPI product (if specified).

### 2. Organization Validation[​](/general/authentication#2-organization-validation "Direct link to 2. Organization Validation")

We ensure the API key is linked to an active organization.

### 3. JWT Token Processing[​](/general/authentication#3-jwt-token-processing "Direct link to 3. JWT Token Processing")

For API keys with JWT authentication enabled:

a. **Token Extraction and Validation**

* We extract and decode the JWT from the Authorization header.
* We verify the token's signature and expiration.

b. **Caching**

* Valid tokens are cached to optimize performance on subsequent requests.

### 4. Spend Management checks[​](/general/authentication#4-spend-management-checks "Direct link to 4. Spend Management checks")

In this step, we perform crucial checks related to the organization's spending:

a. **Daily Threshold Check**

* We verify if the organization has exceeded its daily spending threshold.
* If the threshold has been exceeded, the request is rejected to prevent unexpected overspending.
* This check applies to all requests, regardless of the organization's pay-as-you-go status.

### 5. Quota Checks and Pay-As-You-Go Handling[​](/general/authentication#5-quota-checks-and-pay-as-you-go-handling "Direct link to 5. Quota Checks and Pay-As-You-Go Handling")

Our quota system is designed to provide flexible usage control at both the API key and organization levels, with special considerations for pay-as-you-go accounts.

a. **Organization-Wide Quotas**

* These quotas apply across all API keys associated with an organization and are determined by the organization's subscriptions and committed-use plans.
* They are independent of individual API keys and reflect the overall service level acquired by the organization.
* Typical quota types include:
  + Total data volume limits
  + Aggregate request limits across all keys
  + Access to premium features or data sets

b. **Pay-As-You-Go and Quota Enforcement**

* When pay-as-you-go is enabled for an organization:
  + The system attempts to enforce subscription limits, but due to the distributed nature of our infrastructure, strict enforcement is not guaranteed.
  + There may be small overages ("dust charges") if you rely solely on 429 responses to manage your usage.
  + To avoid unexpected charges, we recommend implementing your own usage tracking in addition to monitoring our 429 responses.
* Account standing is determined by:
  + Current account balance
  + Available post-paid credit limit
* This allows organizations to continue using CoinAPI services beyond their base subscription limits, providing flexibility for unexpected spikes in usage or growing needs.

c. **Billing and Credit Checks**

* For organizations with pay-as-you-go enabled:
  + We check the organization's current account balance and available credit.
  + Usage is allowed to continue as long as the account remains in good standing.
* If the account reaches its credit limit or has outstanding unpaid balances:
  + Further requests may be restricted until the account is brought back into good standing.
* API access will be blocked if both conditions are met:
  + The oldest past due invoice is more than 31 days old
  + The total past due amount exceeds the organization's successful payments from the previous quarter

d. **Autocharge Feature**

* Pay-as-you-go customers can enable the autocharge feature to maintain continuous good standing.
* When enabled, this feature automatically charges the customer's payment method when their balance falls below a specified threshold.
* Benefits of autocharge:
  + Ensures uninterrupted access to CoinAPI services
  + Prevents sudden service interruptions due to exceeding credit limits
  + Simplifies account management for high-volume users
* Customers can set and adjust autocharge thresholds and limits through the Customer Portal.

Special Cases[​](/general/authentication#special-cases "Direct link to Special Cases")
--------------------------------------------------------------------------------------

### Dynamic Quota Adjustment[​](/general/authentication#dynamic-quota-adjustment "Direct link to Dynamic Quota Adjustment")

Our system supports real-time quota adjustments:

* Organization quotas are automatically adjusted when subscription changes or committed-use plan modifications are processed.
* Pay-as-you-go status can be enabled or disabled, affecting how organization quotas are enforced across all services.

### Quota Overage Handling[​](/general/authentication#quota-overage-handling "Direct link to Quota Overage Handling")

Quota overage handling depends on the pay-as-you-go status:

1. For organization quotas:
   * With pay-as-you-go enabled:
     + The system attempts to enforce subscription limits, but small overages may occur.
     + Usage is monitored and billed according to the organization's plan rates, including any overages.
     + If autocharge is enabled, the account is automatically topped up to maintain good standing.
   * Without pay-as-you-go:
     + All API keys for the organization will be restricted when quotas are exceeded.
     + Service resumes when the quota resets (e.g., start of a new billing cycle) or the subscription is upgraded.

Monitoring and Notifications[​](/general/authentication#monitoring-and-notifications "Direct link to Monitoring and Notifications")
-----------------------------------------------------------------------------------------------------------------------------------

We maintain comprehensive monitoring of our authorization layer to ensure system health and optimal performance across all CoinAPI products. This includes tracking various aspects of the authorization process, quota utilization, and account status. Our monitoring system generates notifications for both internal teams and customers when certain thresholds are reached or unusual patterns are detected. This proactive approach allows us to address potential issues quickly and helps customers stay informed about their API usage and account status across all CoinAPI services.

Conclusion[​](/general/authentication#conclusion "Direct link to Conclusion")
-----------------------------------------------------------------------------

Our authorization process is designed to provide secure, flexible, and scalable access to all CoinAPI products. By implementing multi-layered validation, sophisticated quota management based on subscriptions and committed-use plans, and flexible pay-as-you-go options with autocharge capabilities, we ensure that our services remain protected while offering customers the ability to scale their usage according to their needs.

While we strive to enforce the limits, the distributed nature of our infrastructure means that small overages may occur. To avoid unexpected charges, we recommend implementing your own usage tracking in addition to monitoring our 429 responses. This approach ensures the most accurate usage management and helps prevent unintended overages.

The combination of API key-specific controls, organization-wide quotas, and pay-as-you-go flexibility provides a powerful toolset for managing API access and usage across diverse use cases and organizational structures, ensuring uninterrupted service for accounts in good standing across the entire CoinAPI product suite.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Next

Security and Compliance](/general/security)

* [Overview](/general/authentication#overview)
* [Authorization Flow](/general/authentication#authorization-flow)
  + [1. API Key Validation](/general/authentication#1-api-key-validation)
  + [2. Organization Validation](/general/authentication#2-organization-validation)
  + [3. JWT Token Processing](/general/authentication#3-jwt-token-processing)
  + [4. Spend Management checks](/general/authentication#4-spend-management-checks)
  + [5. Quota Checks and Pay-As-You-Go Handling](/general/authentication#5-quota-checks-and-pay-as-you-go-handling)
* [Special Cases](/general/authentication#special-cases)
  + [Dynamic Quota Adjustment](/general/authentication#dynamic-quota-adjustment)
  + [Quota Overage Handling](/general/authentication#quota-overage-handling)
* [Monitoring and Notifications](/general/authentication#monitoring-and-notifications)
* [Conclusion](/general/authentication#conclusion)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.