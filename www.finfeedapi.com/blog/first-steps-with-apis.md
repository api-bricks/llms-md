FinFeedAPI Blog - Your First Steps with APIs. Guide for beginner developers

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fc9a795fc7fb3558997d636211a44e71eb59288f0-773x184.png&w=1920&q=75)![background](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](/)

* Products
* Pricing
* Resources
* [Blog](/blog)
* Contact us
* [Log in](https://console.finfeedapi.com/?link=/apikeys/create)

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fef86f7d148c1fa9e1d0e5d8f813414bc6e06d15c-1440x1800.webp&w=96&q=75)Maciej

May 13, 2025

Your First Steps with APIs. Guide for beginner developers
=========================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F55b0f03360a41f7fc4eddb83c02686919e2679d2-640x426.jpg%3Frect%3D0%2C74%2C640%2C278%26w%3D920%26h%3D400&w=1920&q=75)

As you are starting an exciting path in **software development**, and one of the most fundamental concepts you'll encounter is the API, or **Application Programming Interface**. This post will guide you through what **APIs** are, how **APIs work**, and provide a step-by-step approach to start using them. Gaining a **basic understanding** of APIs will open up a vast range of possibilities for building powerful and **innovative applications**.

What Exactly is an Application Programming Interface (API)?
-----------------------------------------------------------

An **Application Programming Interface** acts as a contract, a set of rules and protocols that allows different **software applications** to communicate and **exchange data** with each other. Think of it as a messenger. Your application (the client) needs some information or wants to perform an action that another piece of software (the **server**) can provide. The API is the messenger that carries your request to the server and brings back the response.

APIs are everywhere in modern software. When you use an app on your phone to check the weather, that app is likely using an API to fetch weather information from a weather service's system. When you log into a website using your Google or Facebook account, that’s an API in action, allowing the website to verify your identity through Google's or Facebook's **systems**. They are crucial for enabling **seamless communication** between diverse pieces of software, allowing **developers** to leverage **existing data** and functionality without having to build everything from scratch. This interaction facilitates the creation of more complex and feature-rich applications.

There are many **types of APIs**. **Web APIs**, which we'll focus on heavily, are designed for use over the internet. You might also encounter **database APIs** that allow applications to interact with databases directly, or **remote APIs** designed for interaction between applications running on different machines across a **communications network**.

How Do APIs Work? The Core Mechanics
------------------------------------

The way **APIs work** generally follows a client-server model.

1. **The Client Sends a Request:** Your application (the client) needs something. This could be to **retrieve data**, add new data, or **update existing resources**. The client constructs an **API call**, which is essentially a request message formatted according to the API's specifications. This request is sent to a specific URL, often called an endpoint, on an **API server**.
2. **The Server Processes the Request:** The **API server** receives the request. It then performs the necessary **server processes**: it might query a database, execute some **code**, or interact with **other systems** to fulfill the request.
3. **The Server Sends a Response:** Once the server has processed the request, it sends a response back to the client. This response typically includes a **status code** indicating whether the request was successful, and the requested **data** (if any) in a specified format.

This exchange of **request messages** and responses allows for an efficient way to **exchange information**. The beauty of APIs is that the client doesn't need to know the internal workings or **complex code** of the server; it just needs to understand the API's contract – how to make requests and interpret responses.

A Closer Look at Web APIs
-------------------------

**Web APIs** are a dominant type of API you'll encounter, especially in **web development**. They use the Hypertext Transfer Protocol (**HTTP protocol**) as their communication standard. Think of HTTP as the language spoken between web clients (like your browser or application) and web servers. **Web services** are a common way to implement **web APIs**, allowing different applications to interact over the web.

Several key components are involved in how **web APIs** function:

* **HTTP Methods:** These verbs define the action you want to perform on a resource. Common **HTTP methods** include:
  + GET: Used to **retrieve data** from a specified resource. For example, getting a list of products.
  + POST: Used to submit data to be processed to a specified resource, often causing a change in state or creation of a new resource. For example, creating a new user account.
  + PUT: Used to **update existing resources** fully. For example, changing all the details of a user profile.
  + PATCH: Used to partially update an existing resource.
  + DELETE: Used to remove a specified resource. For example, deleting a blog post.
* **Endpoints (URLs):** Each function an API offers is exposed via an endpoint, which is a specific URL. For example, an API might have an endpoint like <https://api.example.com/users> to manage user data.
* **HTTP Headers:** Both requests and responses use **HTTP headers** to pass additional information. Headers can include details about authentication (like an **API key**), the format of the data being sent or requested (e.g., Content-Type: application/json), caching instructions, and more.
* **Status Codes:** When an API server responds to a request, it includes an HTTP **status code**. This three-digit number provides a quick way to understand the **system's response**. Some common codes are:
  + 200 OK: The request was successful.
  + 201 Created: The request was successful, and a new resource was created.
  + 400 Bad Request: The server could not understand the request due to invalid syntax.
  + 401 Unauthorized: Authentication is required and has failed or has not yet been provided.
  + 403 Forbidden: The server understood the request, but is refusing to fulfill it (you don't have permission).
  + 404 Not Found: The server could not find the requested resource.
  + 500 Internal Server Error: A generic error message, given when an unexpected condition was encountered by the server.

Understanding these HTTP components is fundamental to working with most **web APIs**.

Exploring Types of Web APIs: REST and SOAP
------------------------------------------

While there are many **different APIs**, two prominent architectural styles for **web APIs** are REST and SOAP.

### **REST APIs (Representational State Transfer)**

**Representational State Transfer**, or REST, is an **architectural style** for designing networked applications. [**REST APIs**](https://www.finfeedapi.com/blog/apis-rest-vs-websocket), often called **RESTful APIs**, adhere to a set of constraints that make them simple, scalable, and easy to use.

Key principles of the **REST architecture** include:

* **Client-Server:** A clear separation between the client (which makes requests) and the server (which sends responses).
* **Stateless:** Each request from a client to a server must contain all the information needed to understand the request. The server does not store any client context between requests.
* **Cacheable:** Responses can be marked as cacheable or non-cacheable to improve performance.
* **Uniform Interface:** This is a core principle and involves:
  + Resource identification in requests (e.g., using URIs like /users/123).
  + Manipulation of resources through representations (e.g., sending JSON or **XML** data to modify a resource).
  + Self-descriptive messages (e.g., responses include status codes and headers like Content-Type).
  + Hypermedia as the Engine of Application State (HATEOAS): Responses can include links to related actions or resources.

**REST APIs** commonly use HTTP methods explicitly and often use JSON as their primary **data format** due to its **easy syntax** and lightweight nature, although they can also use **XML data format** or **plain text**. Many **public APIs**, like the **Twitter API** (though its access rules have changed over time) or APIs for services like **Google Maps**, are designed as **RESTful APIs**.

### **SOAP APIs (Simple Object Access Protocol)**

**Simple Object Access Protocol**, or SOAP, is a protocol, meaning it has stricter rules than REST. **SOAP APIs** have been around longer than REST and are often used in enterprise environments where more formal contracts and advanced security features are needed.

Key characteristics of **SOAP APIs**:

* **Protocol-based:** Relies on a standardized XML-based messaging format.
* **Strict Contract:** Uses Web Services Description Language (WSDL) to define the API's functionality, message formats, and how to interact with it. This WSDL acts as the formal contract.
* **Built-in Error Handling:** The SOAP specification includes standardized error handling.
* **Transport Agnostic:** While commonly used over HTTP, SOAP can technically be used with other protocols like SMTP (email).
* **Uses XML Exclusively:** All request and response messages in **SOAP APIs** are formatted using **Extensible Markup Language (XML)** for **structuring messages**.

SOAP can handle more **complex functions** and transactions, often involving stateful operations. However, this often comes at the cost of increased complexity and overhead compared to REST.

### **REST vs. SOAP: Which to Choose?**

* **REST APIs** are generally preferred for **web application** development and mobile apps because they are simpler, more flexible, and lighter weight. They are easier to work with, especially for **new users**.
* **SOAP APIs** might be chosen for enterprise applications requiring robust security, transactional reliability, and formal contracts, or when integrating with legacy **systems** that already use SOAP.

Understanding Data Formats in APIs
----------------------------------

APIs need a way to structure the **data** they **exchange information** with. Several **data formats** are common:

* **JSON (JavaScript Object Notation):** This is currently the most popular format for **REST APIs**. It's lightweight, human-readable, and has an **easy syntax** that is simple for machines to parse and generate.

```
1{
2  "name": "John Doe",
3  "email": "john.doe@example.com",
4  "userId": 123
5}
6
```

* **XML (Extensible Markup Language):** **XML data format** was the standard for many years, especially with **SOAP APIs**. It uses tags to define elements and structure data. While more verbose than JSON, **XML** is still used in many enterprise **systems** and some **REST APIs**.

```
1<user>
2  <name>John Doe</name>
3  <email>john.doe@example.com</email>
4  <userId>123</userId>
5</user>
```

* **Plain Text:** For very simple data, an API might just return **plain text**.
* **Other Formats:** You might occasionally encounter other **different formats** like CSV (Comma Separated Values) or even binary formats for specific use cases, though JSON and XML are the most prevalent for general **web APIs**.

The **API documentation** will always specify which **data formats** an API supports.

Getting Started with APIs: A Step-by-Step Guide for Beginners
-------------------------------------------------------------

Ready to make your first **API call**? Here's a general process you can follow. This can feel like an "api tutorial" in itself.

### **Step 1: Find an API to Work With**

* **Public APIs:** Many organizations provide **public APIs** that are free to use (though they often have usage limits). These are great for learning. Public API catalogues like [this one](https://github.com/public-apis/public-apis) list hundreds of them across various categories (e.g., weather, movies, games, open data).
* Examples:
  + **JSONPlaceholder:** A fantastic fake online REST API for testing and prototyping. It provides dummy data for users, posts, comments, etc.
  + **OpenWeatherMap API:** Provides weather data (requires an **API key**).
  + While more complex, the **Twitter API** and **Google Maps API** are classic examples of powerful APIs, though they have specific terms of service and authentication requirements.
* **Partner APIs:** These require a business relationship with the API provider.
* **Private APIs:** These are used internally within an organization and are not exposed to the public.

For your first foray, choose a simple public API with clear documentation.

### **Step 2: Read the API Documentation Thoroughly**

The **API documentation** is your most important resource. It's the instruction manual for the API. Look for:

* **Base URL:** The starting URL for all API endpoints.
* **Endpoints:** The specific URLs for different actions or resources (e.g., /users, /products/{id}).
* **Authentication:** How to authenticate your requests (e.g., using an **API key**, OAuth).
* **HTTP Methods:** Which methods (GET, POST, PUT, DELETE, etc.) are supported for each endpoint.
* **Request Parameters:** What data you can (or must) send with your request (e.g., query parameters, request body format).
* **Response Formats:** How the data will be returned (e.g., JSON, **XML**).
* **Rate Limits:** How many requests you can make in a given time period.
* **Error Codes:** Specific error messages and what they mean.
* **Code Samples/API Tutorial:** Many documentations provide code examples in various programming languages.

Good **API documentation** will save you a lot of time and frustration.

### **Step 3: Authentication – Get Your API Key (If Needed)**

Many APIs, especially **public APIs** that offer valuable **data** or services, require authentication to identify and authorize users. The most common method for simpler APIs is an **API key**.

* **What is an API Key?** An **API key** is a unique string of characters that you include in your **API call** to identify your application.
* **How to get one:** You typically need to register on the API provider's developer portal and they will issue you an **API key**.
* **How to use it:** The **API documentation** will specify how to send the **API key** – usually in an **HTTP header** (e.g., Authorization: Bearer YOUR\_API\_KEY or X-API-Key: YOUR\_API\_KEY) or as a query parameter in the URL (e.g., ?apiKey=YOUR\_API\_KEY).

Keep your API keys secret! Do not embed them directly in client-side code that is publicly accessible.

### **Step 4: Make Your First API Call**

Once you have an API endpoint, understand its requirements, and have an **API key** (if needed), you can make an **API call**.

* **Tools for Making API Calls:**
  + **Command Line:** Tools like cURL are powerful for making HTTP requests directly from your terminal. Example: curl -X GET "<https://api.example.com/data?apiKey=YOUR_KEY>"
  + **GUI API Clients:** Applications like Postman or Insomnia provide a user-friendly interface for crafting and sending API requests, viewing responses, and organizing your API interactions. These are highly recommended for beginners.
  + **Programming Languages:**
    - **Python:** The requests library is very popular:

```
1import requests
2response = requests.get("https://jsonplaceholder.typicode.com/todos/1")
3print(response.json())
```

* **JavaScript (Browser/Node.js):** The Workspace API is built-in:

```
1fetch('https://jsonplaceholder.typicode.com/todos/1')
2  .then(response => response.json())
3  .then(json => console.log(json))
```

* **Constructing the Request:** Ensure you have the correct URL, **HTTP method**, any necessary **HTTP headers** (like Content-Type or for the **API key**), and a request body if you're sending data (e.g., with POST or PUT requests).
* **Interpreting the Response:**
  + Check the **status code** first to see if the request was successful.
  + Examine the response headers for additional metadata.
  + If successful, look at the response body to **extract data**. This will likely be in JSON or **XML** format. You'll need to parse this data to use it in your application.

### **Step 5: API Integration in Your Project**

After successfully making API calls and understanding how to **retrieve data** or send it, the next step is **API integration** into your **software applications**. This means writing **code** in your chosen programming language to:

1. Make **API calls** programmatically.
2. Handle responses, including successful data retrieval and error conditions.
3. Use the **data** obtained from the API to display information, power features in your **web application**, or enable communication with **other systems**.
4. Allow your application to **update existing resources** or create new ones via the API if that's part of its functionality.

For instance, a weather widget on a website would make an **API call** to a weather service, **extract data** like temperature and conditions from the response, and then display it to the user.

Working with APIs: Best Practices
---------------------------------

* **Handle Errors Gracefully:** Always check the **status code** and design your application to handle potential errors (e.g., network issues, API errors like 404 or 500).
* **Respect Rate Limits:** APIs often have limits on how many requests you can make per second/minute/day. Exceeding these can get your access temporarily or permanently blocked.
* **Secure Your API Keys:** Never expose your **API key** in client-side JavaScript or commit it to public code repositories. Use environment variables or secure server-side storage.
* **Read Terms of Service:** Understand how you are permitted to use the API and its **data**.
* **Use Libraries/SDKs:** If the API provider offers a Software Development Kit (SDK) for your programming language, it can often simplify **API integration** and handle some of the **complex code** for authentication and request formatting.

The Value APIs Bring to Software Development
--------------------------------------------

Understanding and using APIs is a fundamental skill because they offer numerous benefits:

* **Modularity and Reusability:** Break down **complex functions** into smaller, manageable services.
* **Faster Development:** Leverage existing services and **data** instead of building everything from scratch. This allows you to focus on the unique aspects of your application.
* **Innovation:** Combine **different APIs** from various providers to create new and **innovative applications** and user experiences. For example, mashups that combine mapping data from **Google Maps** with social media data from the **Twitter API**.
* **Seamless Communication:** Allow diverse **software applications**, even those written in different languages or running on different platforms, to **exchange data** and work together.
* **Access to External Data and Functionality:** Easily **access data** and capabilities from third-party services (e.g., payment gateways, cloud storage, social media).

APIs are the building blocks of the modern internet and interconnected **software applications**. As you continue your journey as a **developer**, you'll find yourself interacting with them constantly, whether you're consuming **public APIs**, building your own for **other apps** to use, or integrating with **partner APIs**. Take the time to explore, experiment with a simple **API tutorial** for a service that interests you, and soon you'll be comfortable making **API calls** and using them to build exciting projects. Happy coding!

Stay up to date with the latest FinFeedAPI news

Send

By subscribing to our newsletter, you accept our website terms and privacy policy.

### Recent Articles

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Ff5d281796605b6b3d0e45cc56de84fc716102e7c-920x400.png&w=3840&q=75)

Stock market data APIs

Whats a Stock Index: Definition, Types, and Importance in Investing

A stock index is a collection of company shares that tracks the performance of a specific market segment. By combining the prices of selected stocks, it provides a snapshot of market trends and overall performance](/blog/whats-a-stock-index)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F1d11014f03ff374a2c828a2e5b7dbc27dc4db44a-920x400.png&w=3840&q=75)

Stock market data APIs

FinFeedAPI Now Covers the Stock Exchange of Thailand

FinFeedAPI has expanded its data coverage to include the Stock Exchange of Thailand (SET) [XBKK], one of Southeast Asia's most liquid and established markets. This integration provides direct API access to the Thai market, continuing our mission to offer comprehensive global data through a single, developer-friendly interface.](/blog/finfeed-cover-set-stock-exchange-of-thailand)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F1d5b6ba9d9743e616729cd516369d9713549b3b3-920x400.png&w=3840&q=75)

Exchange rates API

Financial Symbols and Their Meanings: A Complete Guide to Global Currency Symbols

Financial symbols and their meanings form the foundation of global economic communication, enabling trillions of dollars in daily transactions across international borders. From the universally recognized dollar sign to emerging cryptocurrency symbols, these visual representations continue evolving alongside our changing global economy.](/blog/financial-symbols-and-their-meanings)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb374c99676570587856b9d56f1c76f9f6a3ec28f-920x400.png&w=3840&q=75)

Stock market data APIs

Essential Stock Market Terms: Complete Guide for Investors in 2025

Whether you’re reading analyst reports, evaluating potential investments, or executing trades, knowing the language of Wall Street is essential. This guide covers the most important stock market terms every investor should master, from basic concepts to advanced strategies that can enhance your investment strategy.](/blog/essential-stock-market-terms)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F819c61799d42674a7cdffa6adba96f22f86d4341-920x400.png&w=3840&q=75)

Stock market data APIs

Ticker Symbol for Stock Market: Complete Guide to Stock Identification

Whether you’re researching your first stock purchase or trying to understand financial news websites, mastering ticker symbols is essential for navigating the stock market effectively. This comprehensive guide will walk you through everything you need to know about these crucial market identifiers.](/blog/ticker-symbol-for-stock-market)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F68905fb6b11d4873535f8eb71d6d915591151ca2-920x400.png&w=3840&q=75)

Exchange rates API

Over 80 New Currencies Added to Currencies API

Our FX Realtime and Historical REST APIs have been updated to support an expanded list of fiat currencies. The service now includes data for over 250 currencies, increasing the geographical scope of available exchange rate data to include more markets across Africa, Asia, Europe, the Americas, and Oceania.](/blog/currencies-api-80-new-currencies)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F576399cd8818961aa8958e890f011c9f77affe8e-920x400.png&w=3840&q=75)

Stock market data APIs

FinFeedAPI Adds Coverage for the Jamaica Stock Exchange (XJAM)

FinFeedAPI has expanded its data coverage to include the Jamaica Stock Exchange (XJAM), providing direct API access to a key Caribbean financial market. This addition is part of our ongoing effort to provide comprehensive, global market data through a single, unified interface.](/blog/finfeedapi-adds-jamaica-stock-exchange)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fded24160df10dcb70b8f4d7103188527f4f5a776-920x400.png&w=3840&q=75)

Stock market data APIs

New Markets, New Opportunities: FinFeedAPI Welcomes Spotlight, New Zealand, and Prague Exchanges

We are excited to share a major update to our data offerings. FinFeedAPI now provides direct API access to three additional European and Asia-Pacific stock exchanges: the Spotlight Stock Market (XSAT), the New Zealand Stock Exchange (XNZE), and the Prague Stock Exchange (XPRA).](/blog/new-exchanges-spotlight-new-zealand-prague)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F918183f3c09da9d691de108abe90afbed1e2a70d-920x400.png&w=3840&q=75)

API technology

API Market Trends: Top Platforms to Buy, Sell, and Integrate APIs

Curious about the API market? This article explores the latest trends, must-know platforms, and how API marketplaces support developers and businesses in the tech ecosystem.](/blog/api-market-trends)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fac972de386f9a1e8586c7eadbb12a39680c68eb9-920x400.png&w=3840&q=75)

API technology

Stop Babysitting Your AI: A Developer’s Guide to Self-Sufficient Financial Agents with MCP APIs

Stop babysitting your AI. Learn how developers can use FinFeedAPI's machine-readable APIs to build autonomous agents that intelligently analyze SEC, stock, and FX data](/blog/self-sufficient-financial-agents-with-mcp-apis)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb9058ff6698f7f327be6f5628681e35092e857a9-920x400.png&w=3840&q=75)

API technology

FinFeed API is compatible with MCP

Your AI just learned to speak finance: Say goodbye to API integration headaches](/blog/finfeed-api-mcp-compability)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F1be57bde0d03d7a664a2dbfc1f0995e1bd7ba109-920x400.png&w=3840&q=75)

Flat files, Stock market data APIs

API vs. Flat File: A Fintech Developer's Grudge Match

Developers, stop guessing. Learn when to use a real-time REST API versus a batch flat file for financial data. Our guide covers security, scalability, and real-world anecdotes.](/blog/api-vs-flat-file)

### Get your free API key now and start building in seconds!

[Get API Key](https://console.finfeedapi.com/?link=/apikeys/create)[Read Docs](https://docs.finfeedapi.com/)

[![background](https://cdn.sanity.io/images/xpx4czto/production/8a2788aebc71f7f5dce82eb1b7a5e5cec9a64838-773x184.svg)](/)

###### Join our newsletter

* [![Slack](https://cdn.sanity.io/images/xpx4czto/production/26371f7c1474b3ce9e67c32e006a140ddd704b95-512x512.svg)](https://finfeedapi.slack.com/x-p8539721774929-8529109118914-8531038476964/messages/C08FVM7P68H)
* [![X](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2F0aa41878d0ceb77292d9f847b2f4e21d688460c1-2400x2453.png&w=64&q=75)](https://x.com/FinFeedAPI "Follow FinFeedAPI on X")
* [![LinkedIn](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fxpx4czto%2Fproduction%2Fb9ce6f119974543779bbcad7563e234be8edd900-840x779.png&w=64&q=75)](https://www.linkedin.com/company/finfeedapi/?viewAsMember=true "Join FinFeedAPI on LinkedIn")
* [![GitHub](https://cdn.sanity.io/images/xpx4czto/production/f202b6faccfd5cc46299b976c2635fee60b55aa0-98x96.svg)](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi)

###### Products

###### Products

* [Stock API](/products/stock-api)
* [Currencies API](/products/currencies-api)
* [SEC API](/products/sec-api)

###### Use cases

###### Use cases

* [AI agents](/use-case/ai-agents)
* [Backtesting & strategy simulation](/use-case/backtesting-strategy-simulation)
* [Compliance & regulatory monitoring](/use-case/compliance-regulatory-monitoring)
* [E-commerce](/use-case/e-commerce)
* [Financial data platforms](/use-case/financial-data-platforms)
* [Financial education](/use-case/education-platforms)
* [Investment research & analytics](/use-case/investment-research-analytics)
* [Machine learning](/use-case/machine-learning)
* [Market analysis](/use-case/market-analysis)
* [Portfolio management](/use-case/portfolio-management)
* [Remittance](/use-case/remittance)
* [Risk management](/use-case/risk-management)
* [Trading platforms](/use-case/trading-platforms)
* [Travel & hospitality](/use-case/travel-hospitality)

###### Resources

###### Resources

* [Glossary](/learn/glossary)
* [Documentation](https://docs.finfeedapi.com/)
* [Status page](https://status.finfeedapi.com/)
* [SDK](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi)
* [Tutorials](https://github.com/api-bricks/api-bricks-sdk/tree/master/finfeedapi/sec-api-rest/tutorials)
* [Brand assets](https://brandfetch.com/finfeedapi.com)

###### Legal

###### Legal

* [Customer agreement](/legal#link-479af90ac5b8)
* [Acceptable usage policy](/legal#link-469068dc1416)
* [Privacy policy](/legal#link-192d9f962f94)

###### Contact

###### Contact

* [Contact us](/contact-us)

###### API Bricks brands

###### API Bricks brands

* [CoinAPI.io](https://www.coinapi.io/?utm_source=finfeedapi&utm_medium=referral&utm_campaign=finfeedapi_footer)

![background](https://cdn.sanity.io/images/xpx4czto/production/33a64ee50c88a79ba86cc35ba36e9eb13987bbe7-152x184.svg)Copyright 2025 API BRICKS LTD or its affiliates. All rights reserved.