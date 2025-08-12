Billing | FinFeedAPI.com Documentation




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

  + [Home](/general/customer-portal/home)
  + [Billing](/general/customer-portal/billing)
  + [Subscriptions](/general/customer-portal/subscriptions)
  + [API Keys](/general/customer-portal/APIKeys)
  + [Traces](/general/customer-portal/Traces)
  + [Usage Metrics](/general/customer-portal/UsageMetrics)
  + [Metered Usage](/general/customer-portal/MeteredUsage)
  + [Support Tickets](/general/customer-portal/SupportTickets)
  + [Quotas and Limits](/general/customer-portal/QuotasLimits)
  + [Notifications](/general/customer-portal/Notifications)
  + [Account](/general/customer-portal/Account)
* [MCP Servers](/general/mcp-servers)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [Customer Portal](/general/customer-portal/)
* Billing

On this page

Billing
=======

Overview[​](/general/customer-portal/billing#overview "Direct link to Overview")
--------------------------------------------------------------------------------

This is your **Overview page** within the Billing section. It gives you a snapshot of your organization's financial status and related settings.

The page is divided into several key areas:

* **Your Credit Balance**

  + **Total Credits** - This is the total number of usage credits (gross) you've purchased or have been granted.
  + **Usage This Period** - Credits used so far in the current billing cycle that will be on your next invoice (may include usage from previous periods that has not yet been invoiced).
  + **Remaining Credits** - This is your balance of purchased credits after accounting for your uninvoiced usage.
* **Your Available Usage**

  + **Remaining Credits** - The credits you currently have left on your account net of uninvoiced usage.
  + **Overage Protection** - Your allowance to continue using the service on negative balance. Any usage from this protection will be billed on your next invoice. This credit line is enabling possibility to overage subscriptions without having to pay for it upfront (post-paid).
  + **Spend Management Daily Hard Limit** - Credits used today against your daily hard limit. When the limit is reached, further usage is blocked until the next day.
  + **Available to Use** - This is the total number of credits available to you right now.
* **Invoice Address** section displays the company name for billing. You have a direct option to "Edit address" here.
* **Invoice Billing Email** section indicates the specific email address where invoices and billing correspondence should be sent. You can use the "Edit email" button to configure this and set a dedicated invoice notification.
* **The auto-recharge** section indicates if this feature is "Disabled" or “Enabled”. There's a "Modify" button available to change this setting.
* **Spend Management** section shows whether this functionality is disabled or enabled for your team. There's a "Modify" button available to change this setting.

Invoices[​](/general/customer-portal/billing#invoices "Direct link to Invoices")
--------------------------------------------------------------------------------

This is your **Invoices page,** located within the Billing section. It's designed to give you a clear overview of your payments and order history.

The page is organized into two main parts:

* **Payments Due:** This section is set up to list any outstanding payments. You will see columns for the Invoice Date, Invoice ID, Due Date, the Amount owed, and an Actions column for managing them.
* **Order and invoice history:** Below "Payments Due," this section is intended to display a record of your past orders and invoices. For each entry, you will find the Invoice Date, Invoice ID, Payment date, the Amount, and an Actions column.

Payments Methods[​](/general/customer-portal/billing#payments-methods "Direct link to Payments Methods")
--------------------------------------------------------------------------------------------------------

This is your **Payment Methods page**, located within the Billing section. This is where you manage the payment options linked to your account.

The main part of the page is set up to display a list of your saved payment methods. For each card, you can see: **Credit Card** type and its last few digits, **Name on card, Expiring** date, **Status** column shows which card is the "Default Card." For other cards, a "Set as Default" button is available, allowing you to change your primary payment method.

Each listed card also has a delete icon (a trash can), giving you the option to remove a specific payment method.

To add a payment method, you have a clear call to action with the "**Add New Credit Card**" button on the right side of the screen.

Spend Management[​](/general/customer-portal/billing#spend-management "Direct link to Spend Management")
--------------------------------------------------------------------------------------------------------

This is your **Spend Management page**, located within the Billing section. This page specifically allows you to control and monitor your organization's credit usage and expenses.

The page features several key components for managing your spending:

* A **Spend Management toggle switch** is at the top. When active, it allows you to set usage credit spend amounts, configure notifications, set up webhooks, and define budget limits.
* **Credits Consumed Today** and **Credits Consumed Yesterday** sections help you track your recent credit usage.
* **Set daily credit usage budget**. You can enter a dollar amount here. If your organization's usage exceeds this budget in a day (UTC), any new connections or API calls will be rejected until the end of that day.
* **Set a daily credit usage email notification threshold.** You can enter a dollar amount here. If your usage surpasses this threshold in a day (UTC), an email notification will be sent.
* **Set a webhook URL**. This allows you to provide a URL that will receive a POST request when a notification threshold or your budget amount is reached, enabling real-time alerts to your own systems or services.
* There's a "**Save Changes**" button at the bottom to apply any adjustments you make to these settings.

Add Usage Credits[​](/general/customer-portal/billing#add-usage-credits "Direct link to Add Usage Credits")
-----------------------------------------------------------------------------------------------------------

This is your **Add Usage Credits page**, located within the Billing section. This is where you can add funds to your account balance.

The page asks, "How much would you like to add to your balance?" and provides the following options to do so:

* **Payment amount:** You'll find an input field where you can enter the desired dollar amount. There's a note below it specifying that you should "Enter an amount between $5 and $5000."
* **Select a payment method:** There's a dropdown menu, currently showing "Select Method," which you can use to choose from your saved payment methods or via Cryptocurrency.
* **Add new payment method +:** Just below the dropdown, there's an option to "Add new payment method +" if you need to use a card not already on file.
* Finally, once you've entered the amount and selected a payment method, you can click the "**Add to my balance**" button to complete the transaction.

Auto Recharge[​](/general/customer-portal/billing#auto-recharge "Direct link to Auto Recharge")
-----------------------------------------------------------------------------------------------

This is your **Auto Recharge page**, located within the Billing section. Its purpose is to help you keep your service running without interruption by automatically adding funds to your account.

The page clearly explains the feature: "Keep your service running by setting up auto-recharge. When your balance reaches a certain threshold, we will automatically charge your card."

The main part of the page features:

* **Setting to Auto Recharge:** This includes a toggle switch. You can use this toggle to enable or disable the auto-recharge functionality.
* A "**Save changes**" button is present, which you can click to apply your choice regarding the auto-recharge setting.

Invoice Address[​](/general/customer-portal/billing#invoice-address "Direct link to Invoice Address")
-----------------------------------------------------------------------------------------------------

This is your **Invoice Address page**, located within the Billing section. It's where you manage the address details used for your invoices. The page provides a form for your invoice address details:

* **Company Name:**
* **Address 1:**
* **Address 2:**
* **City:**
* **Postal code:**
* **Region/Province:**
* **Country:**
* **Purchase order (PO) number:**

After you've entered or updated your address information, you can click the "**Save changes**" button to apply them.

Invoice Notifications[​](/general/customer-portal/billing#invoice-notifications "Direct link to Invoice Notifications")
-----------------------------------------------------------------------------------------------------------------------

This is your **Invoice Notifications page**, located within the Billing section. Its purpose, as indicated by the "Billing email" heading and the accompanying note "Invoices and other billing notifications will be sent here," is to specify where your billing communications are directed. On this page, you'll find an "Email" input field, ready for you to enter or update the desired email address. Once you've provided the email, you click the "Updates" button to save this preference.

Tax Settings[​](/general/customer-portal/billing#tax-settings "Direct link to Tax Settings")
--------------------------------------------------------------------------------------------

This is your **Tax Settings page**, located within the Billing section. It's designed to help you configure your tax information for accurate billing and compliance.

At the top right, you'll find an "**Add Tax Registration**" button, allowing you to include new tax details. Below this, the page displays a list of your current tax registrations in a table format. This table shows important details for each entry, including an Id, the Country, a Description (such as "European VAT number"), the specific tax Value or number, and its current Status: "unverified" with a red badge, or "verified" with a black badge.

Balance History[​](/general/customer-portal/billing#balance-history "Direct link to Balance History")
-----------------------------------------------------------------------------------------------------

This is your **Balance History page**, located within the Billing section.

The table below presents a detailed listing of all your balance transactions. Each row in this table provides an Id for the transaction, a Description (such as "Stripe Payment Intent... via Auto Recharge call.," "Applied credit balance to invoice," or "Free Trial Credits"), the Created Time showing the date and time of the transaction, and the Amount in USD. You'll notice that credits are shown as positive amounts, while debits are indicated with a negative value.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Home](/general/customer-portal/home)[Next

Subscriptions](/general/customer-portal/subscriptions)

* [Overview](/general/customer-portal/billing#overview)
* [Invoices](/general/customer-portal/billing#invoices)
* [Payments Methods](/general/customer-portal/billing#payments-methods)
* [Spend Management](/general/customer-portal/billing#spend-management)
* [Add Usage Credits](/general/customer-portal/billing#add-usage-credits)
* [Auto Recharge](/general/customer-portal/billing#auto-recharge)
* [Invoice Address](/general/customer-portal/billing#invoice-address)
* [Invoice Notifications](/general/customer-portal/billing#invoice-notifications)
* [Tax Settings](/general/customer-portal/billing#tax-settings)
* [Balance History](/general/customer-portal/billing#balance-history)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.