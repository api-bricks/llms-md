How should I document and troubleshoot CoinAPI connectivity issues? | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/API-Access-and-Integration/How-should-I-document-and-troubleshoot-CoinAPI-connectivity-issues)

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

  + [General](/general/faq/general/)
  + [API Usage and Limits](/general/faq/API-Usage-and-Limits/)
  + [Billing, Payment, and Subscriptions](/general/faq/Billing-Payment-and-Subscriptions/)
  + [Account Management](/general/faq/Account-Management/)
  + [Security and Privacy](/general/faq/Security-and-Privacy/)
  + [API Access & Integration](/general/faq/API-Access-and-Integration/)

    - [Can using a VPN affect my connection to CoinAPI?](/general/faq/API-Access-and-Integration/Can-using-a-VPN-affect-my-connection-to-CoinAPI)
    - [How can I fix certificate validation errors when connecting to CoinAPI?](/general/faq/API-Access-and-Integration/How-can-I-fix-certificate-validation-errors)
    - [How can I troubleshoot FIX API logon issues with CoinAPI?](/general/faq/API-Access-and-Integration/How-can-I-troubleshoot-FIX-API-logon-issues-with-CoinAPI)
    - [How can I use CoinAPI from MATLAB?](/general/faq/API-Access-and-Integration/How-can-I-use-CoinAPI-from-MATLAB)
    - [How do I generate an API key for FIX API access?](/general/faq/API-Access-and-Integration/How-do-I-generate-an-API-key-for-FIX-API)
    - [How do I troubleshoot API errors?](/general/faq/API-Access-and-Integration/How-do-I-troubleshoot-API-errors)
    - [How does CoinAPI calculate cryptocurrency exchange rates?](/general/faq/API-Access-and-Integration/How-does-CoinAPI-calculate-cryptocurrency-exchange-rates)
    - [How should I document and troubleshoot CoinAPI connectivity issues?](/general/faq/API-Access-and-Integration/How-should-I-document-and-troubleshoot-CoinAPI-connectivity-issues)
    - [What programming languages are supported by CoinAPI?](/general/faq/API-Access-and-Integration/What-programming-languages-are-supported-by-CoinAPI)
    - [What timezone does CoinAPI use for date and time values?](/general/faq/API-Access-and-Integration/What-timezone-does-CoinAPI-use-for-date-and-time)
    - [Where are CoinAPI’s servers located, and how does latency vary by region?](/general/faq/API-Access-and-Integration/Where-are-CoinAPI-servers-located)
    - [Where can I find API examples and SDK source code for CoinAPI?](/general/faq/API-Access-and-Integration/Where-can-I-find-API-examples-and-SDK-source-code)
    - [Why am I getting an "Invalid API Key" error after generating a new key?](/general/faq/API-Access-and-Integration/Why-am-I-getting-an-invalid-API-Key-error-after-generating-a-new-key)
    - [Why does my WebSocket connection keep disconnecting with code 1006 and no reason?](/general/faq/API-Access-and-Integration/Why-does-my-WebSocket-connection-keep-disconnecting-with-code-1006-and-no-reason)
  + [Market Data API](/general/faq/Market-Data-API/)
  + [EMS Trading API](/general/faq/EMS-Trading-API/)
  + [Indexes API](/general/faq/Indexes-API/)
  + [Flat Files API](/general/faq/Flat-Files-API/)
  + [Exchange Rates API](/general/faq/Exchange-Rates-API/)
  + [Node as a Service](/general/faq/Node-as-a-Service/)
  + [Enterprise Plan](/general/faq/Enterprise-Plan/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [FAQ](/general/faq/)
* [API Access & Integration](/general/faq/API-Access-and-Integration/)
* How should I document and troubleshoot CoinAPI connectivity issues?

How should I document and troubleshoot CoinAPI connectivity issues?
===================================================================

If you're experiencing connection issues with CoinAPI, please follow the steps below before submitting a support request:

1. Check CoinAPI's Status Page

   Confirm there are no ongoing service disruptions at:

   <https://status.coinapi.io/>
2. Verify DNS resolution

   Use the `dig` command to check domain name resolution:

   ```
   pgsql  
     
   dig [domain name here]
   ```

   A correct response includes an ANSWER SECTION with IP resolution like:

   ```
   lua  
     
   ;; ANSWER SECTION:  
   fix.coinapi.io. IN CNAME api.coinapi.io.  
   api.coinapi.io. IN CNAME api.coinapi.net.  
   ...  
   hdc1-enc-02-bay-08.coinapi.net. IN A 185.204.225.28
   ```

   If the ANSWER SECTION is missing, this indicates a DNS resolution issue.
3. Check TCP connectivity

   Use `nc` to verify port access:

   ```
   cs  
   nc -v [hostname] -p [port]
   ```

   Expected output:

   ```
   css  
     
   Connection to fix.coinapi.io 3302 port [tcp/*] succeeded!
   ```

   If the command fails, analyze the TCP connectivity on your side before contacting support.
4. Test encryption behavior

   Try switching between HTTPS and HTTP endpoints. If the issue appears only with one type, document that in your report—it helps isolate encryption-related errors.
5. Capture a PCAP dump for analysis

   Use `tcpdump` to capture traffic. Adjust the port according to the API protocol:

   * REST or WebSocket API:

     ```
     bash  
       
     tcpdump -i [interface] port 80 or port 443 -w dump.$(date +"%Y%m%dT%H%M%S").cap
     ```
   * FIX API:

     ```
     bash  
       
     tcpdump -i [interface] port 3302 or port 3303 -w dump.$(date +"%Y%m%dT%H%M%S").cap
     ```
6. Analyze the PCAP file before submission

   Ensure:

   * CoinAPI is on the other end of the connection
   * The problem is not caused by internal proxies, gateways, or firewall misbehavior
   * The capture was performed from a system directly connected to the internet (not behind NAT if possible)
7. Submit a support request

   Submit a request at: <https://support.coinapi.io/>

   Include:

   * Accurate problem description with UTC timestamps
   * Results of the DNS (`dig`) and TCP (`nc`) checks
   * A PCAP file with analysis details
   * Set the issue priority according to impact:
     + Urgent – Production system down
     + High – Production system impaired
     + Normal – Feature/system partially affected
     + Low – General guidance or questions

This structured process ensures the support team can respond efficiently and effectively to network-related issues.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

How does CoinAPI calculate cryptocurrency exchange rates?](/general/faq/API-Access-and-Integration/How-does-CoinAPI-calculate-cryptocurrency-exchange-rates)[Next

What programming languages are supported by CoinAPI?](/general/faq/API-Access-and-Integration/What-programming-languages-are-supported-by-CoinAPI)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.