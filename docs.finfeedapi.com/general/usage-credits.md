Usage Credits System | FinFeedAPI.com Documentation




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

* Usage Credits

On this page

FinFeedAPI Usage Credits System
===============================

Overview[​](/general/usage-credits#overview "Direct link to Overview")
----------------------------------------------------------------------

FinFeedAPI implements a flexible usage credits system to provide customers with various options for accessing and paying for our services. This document outlines the key aspects of our usage credits mechanism, focusing on acquisition methods, usage, and billing across our product suite.

Acquiring Usage Credits[​](/general/usage-credits#acquiring-usage-credits "Direct link to Acquiring Usage Credits")
-------------------------------------------------------------------------------------------------------------------

Usage credits can be obtained through several methods:

1. **Promotions and Free Trials**: FinFeedAPI occasionally offers promotional credits or free trial periods to new or existing customers. Every qualified organization receives $25 USD in credits. To be considered qualified, the organization must not be a duplicate of an existing organization.
2. **Manual Purchase**: Customers can buy credits directly through the Customer Portal using either cryptocurrency or fiat currency.
3. **Auto-Recharge Feature**: This automated system adds service credits using the account's payment methods when the balance falls below a certain threshold, bringing it back to a specified level.
4. **Sales Order Form**: Customers can request an order form from our sales team to acquire usage credits, which may include special pricing or terms.

It's important to note that usage credits are generally not limited to specific products unless they were acquired through a sales order form (method 4). In such cases, credits purchased at a discount may be restricted to use with specific products.

Spend Management System[​](/general/usage-credits#spend-management-system "Direct link to Spend Management System")
-------------------------------------------------------------------------------------------------------------------

FinFeedAPI has implemented a comprehensive spend management system to replace the previous pay-as-you-go option. This system provides customers with greater control over their usage and expenses. Here are the key features:

1. **Credit Usage Tracking**:

   * View your daily credit consumption
   * See credits consumed today and yesterday
2. **Daily Credit Usage Budget**:

   * Set a daily budget limit for credit usage
   * If exceeded, new connections and API calls will be rejected until the end of the day (UTC)
3. **Notifications**:

   * Set a customizable daily credit usage threshold
   * Receive email notifications when the threshold is exceeded
   * Configure a webhook URL for real-time notifications:
     + Receive a POST request when a specified credit amount is reached
     + Set up separate webhooks for hard limits and notify limits
     + Integrate with services like PagerDuty to alert your organization's team
   * Webhook payload includes detailed information about the limit reached, current usage, and other relevant data
4. **Webhook Integration**:

   * Configure a webhook URL
   * Receive a POST request when a specified credit amount is reached

These features provide greater visibility and control over your credit usage, helping you manage your expenses more effectively.

Usage Limit Enforcement[​](/general/usage-credits#usage-limit-enforcement "Direct link to Usage Limit Enforcement")
-------------------------------------------------------------------------------------------------------------------

Due to the distributed nature of our system, there are some important considerations regarding usage limit enforcement:

* We check usage limits every 1 minute.
* It's possible that during this interval, usage may temporarily exceed the set limit.
* We strive to reject requests exceeding your plan limits or spend management thresholds as quickly as possible, typically within a short period after the limit is reached.
* Please note that there might be a brief period where usage above the limit is possible before restrictions are applied.
* This applies to both subscription plan limits and spend management features like daily credit usage budgets.

These characteristics are important to keep in mind when managing your usage and configuring spend controls.

Subscription and Quota Interaction[​](/general/usage-credits#subscription-and-quota-interaction "Direct link to Subscription and Quota Interaction")
----------------------------------------------------------------------------------------------------------------------------------------------------

Subscriptions typically grant certain features or usage quotas. Usage beyond these quotas is managed through the spend management system. For example:

* If an organization has a subscription quota of 50,000 credits
* The spend management system allows setting daily budgets and thresholds beyond this quota
* Usage above the quota will be deducted from the available credit balance, subject to the configured spend management settings

Taxation and Expiration[​](/general/usage-credits#taxation-and-expiration "Direct link to Taxation and Expiration")
-------------------------------------------------------------------------------------------------------------------

* Tax is collected at the time usage credits are acquired
* Usage credits do not expire

Monthly Invoicing[​](/general/usage-credits#monthly-invoicing "Direct link to Monthly Invoicing")
-------------------------------------------------------------------------------------------------

Usage is typically invoiced once per month for the previous month's activity. The invoice details the usage and deducts the usage credits, with the amount due being only for usage exceeding the credit balance.

For customers with existing subscriptions, we offer the option to align the usage credit billing period with their subscription billing cycle. This synchronization helps simplify accounting and provides a more comprehensive view of total service costs.

Pre-paid vs Post-paid Usage[​](/general/usage-credits#pre-paid-vs-post-paid-usage "Direct link to Pre-paid vs Post-paid Usage")
-------------------------------------------------------------------------------------------------------------------------------

* **With Subscription**: Organizations with subscriptions are provided a certain level of usage credits that can be paid post-paid, as they have established regular payments.
* **Without Subscription**: Customers without subscriptions are allowed only pre-paid usage, meaning usage credits must be added to the account before usage occurs.

Refund Policy[​](/general/usage-credits#refund-policy "Direct link to Refund Policy")
-------------------------------------------------------------------------------------

Usage credits, once acquired, are non-refundable.

Best Practices for Managing Usage Credits[​](/general/usage-credits#best-practices-for-managing-usage-credits "Direct link to Best Practices for Managing Usage Credits")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. **Monitor Usage**: Regularly check your usage in the Customer Portal to avoid unexpected charges.
2. **Set Appropriate Budgets**: Utilize the daily credit usage budget feature to control your spending.
3. **Configure Notifications**: Set up email notifications to stay informed about your credit usage.
4. **Plan Ahead**: For large projects, consider purchasing credits in advance to ensure uninterrupted service.
5. **Review Invoices**: Carefully review monthly invoices to understand your usage patterns and optimize your credit purchases.
6. **Utilize Spend Management Features**: Take full advantage of the spend management tools in the Customer Portal to control and monitor your credit usage effectively.

Conclusion[​](/general/usage-credits#conclusion "Direct link to Conclusion")
----------------------------------------------------------------------------

FinFeedAPI's usage credits system, combined with the new spend management features, is designed to provide flexibility, transparency, and control in how customers access and pay for our services. By offering multiple acquisition methods, clear usage policies, detailed invoicing, and robust spend management tools, we aim to accommodate diverse customer needs while maintaining a fair and understandable billing process. The replacement of the pay-as-you-go option with the spend management system ensures that customers have even greater control over their usage and expenses. Whether you're a small startup or a large enterprise, our usage credits system can be tailored to suit your specific requirements and usage patterns across the entire FinFeedAPI product suite.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Throttling](/general/throttling)[Next

Customer Portal](/general/customer-portal/)

* [Overview](/general/usage-credits#overview)
* [Acquiring Usage Credits](/general/usage-credits#acquiring-usage-credits)
* [Spend Management System](/general/usage-credits#spend-management-system)
* [Usage Limit Enforcement](/general/usage-credits#usage-limit-enforcement)
* [Subscription and Quota Interaction](/general/usage-credits#subscription-and-quota-interaction)
* [Taxation and Expiration](/general/usage-credits#taxation-and-expiration)
* [Monthly Invoicing](/general/usage-credits#monthly-invoicing)
* [Pre-paid vs Post-paid Usage](/general/usage-credits#pre-paid-vs-post-paid-usage)
* [Refund Policy](/general/usage-credits#refund-policy)
* [Best Practices for Managing Usage Credits](/general/usage-credits#best-practices-for-managing-usage-credits)
* [Conclusion](/general/usage-credits#conclusion)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.