S3 API | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/s3-api/)

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

* [Flat Files](/flat-files-api/)
* [Data & Structure](/flat-files-api/data-types/)
* [Snowflake Access](/flat-files-api/snowflake/)
* [S3 API](/flat-files-api/s3-api/)

  + [Introduction](/flat-files-api/s3-api/)
  + [Authentication](/flat-files-api/s3-api/authentication)
  + [SDK Guide](/flat-files-api/s3-api/sdk)
* [Push API](/flat-files-api/rest-api/push-api)

* S3 API

On this page

S3 API
======

Flat Files S3 API - Comprehensive Documentation
===============================================

Introduction[​](/flat-files-api/s3-api/#introduction "Direct link to Introduction")
-----------------------------------------------------------------------------------

The Flat Files S3 API is a powerful and flexible solution for accessing historical cryptocurrency market data. This document provides in-depth information about the API's features, usage, and integration capabilities.

General Overview[​](/flat-files-api/s3-api/#general-overview "Direct link to General Overview")
-----------------------------------------------------------------------------------------------

### What is Flat Files S3 API?[​](/flat-files-api/s3-api/#what-is-flat-files-s3-api "Direct link to What is Flat Files S3 API?")

Flat Files S3 API is a RESTful API designed to provide efficient access to cryptocurrency market data stored in flat files. The API is built to be compatible with Amazon S3, allowing users to leverage existing S3-compatible tools and infrastructure. While it doesn't support all Amazon S3 features, it focuses on core functionality for listing and downloading files, making it ideal for retrieving historical market data.

### Key Features[​](/flat-files-api/s3-api/#key-features "Direct link to Key Features")

1. S3 Compatibility: Seamless integration with existing S3 tools and libraries.
2. Efficient Data Retrieval: Optimized for listing and downloading large datasets.
3. Flexible Authentication: Supports multiple authentication methods for secure access.
4. Comprehensive Market Data: Access to various data types including trades, quotes, order books, and more.

API Specifications[​](/flat-files-api/s3-api/#api-specifications "Direct link to API Specifications")
-----------------------------------------------------------------------------------------------------

### Implemented Standards[​](/flat-files-api/s3-api/#implemented-standards "Direct link to Implemented Standards")

The Flat Files S3 API adheres to the following HTTP standards:

* [HTTP/1.0](https://datatracker.ietf.org/doc/html/rfc1945)
* [HTTP/1.1](https://datatracker.ietf.org/doc/html/rfc2616)
* [HTTP/2.0](https://datatracker.ietf.org/doc/html/rfc7540)

This ensures broad compatibility and reliable performance across various client implementations.

### Endpoints[​](/flat-files-api/s3-api/#endpoints "Direct link to Endpoints")

The API is accessible through the following endpoints:

| Environment | Encryption | Endpoint URL |
| --- | --- | --- |
| Production | Yes | `https://s3.flatfiles.coinapi.io/` |
| Production | No | `http://s3.flatfiles.coinapi.io/` |

We strongly recommend using the HTTPS endpoint for production environments to ensure data security.

### HTTP Requests[​](/flat-files-api/s3-api/#http-requests "Direct link to HTTP Requests")

For all requests to the Flat Files S3 API, you must include the following header:

```
Accept: application/xml
```

This header indicates that the client expects XML-formatted responses, which is the standard output format for this API.

Authentication[​](/flat-files-api/s3-api/#authentication "Direct link to Authentication")
-----------------------------------------------------------------------------------------

Secure access to the Flat Files S3 API is crucial. For detailed instructions on authentication methods, please refer to the [authentication section](/flat-files-api/s3-api/authentication) of our documentation. This section covers various authentication techniques compatible with S3 clients, including:

* API Key usage
* AWS Signature Version 2 and 4
* Configuration examples for popular S3 clients and SDKs

Supported Operations[​](/flat-files-api/s3-api/#supported-operations "Direct link to Supported Operations")
-----------------------------------------------------------------------------------------------------------

The Flat Files S3 API supports a subset of Amazon S3 REST API operations, tailored for efficient data retrieval. Below are the key operations available:

### List Objects GET[​](/flat-files-api/s3-api/#list-objects-get "Direct link to list-objects-get")

This operation allows you to retrieve a list of objects (files) in the bucket. It corresponds to the [ListObjectsV2](https://docs.aws.amazon.com/AmazonS3/latest/API/API_ListObjectsV2.html) operation in Amazon S3.

#### Usage Notes[​](/flat-files-api/s3-api/#usage-notes "Direct link to Usage Notes")

* This operation is optimized for listing files within the Flat Files S3 API context.
* While it doesn't require all parameters from the Amazon S3 ListObjectsV2 operation, including additional parameters should not affect the result.
* For best practices, stick to the request syntax presented in the HTTP Request section.

#### HTTP Request[​](/flat-files-api/s3-api/#http-request "Direct link to HTTP Request")

1. To list all objects:

   ```
   GET /bucket/?
   ```
2. To list objects with a specific prefix:

   ```
   GET /bucket/?prefix={prefix}
   ```

#### URL Parameters[​](/flat-files-api/s3-api/#url-parameters "Direct link to URL Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| prefix | string | Path prefix to filter the desired files |

#### Example Request[​](/flat-files-api/s3-api/#example-request "Direct link to Example Request")

* shell
* csharp
* php
* python
* js
* go
* ruby
* java

```
curl -X GET -H "Accept: application/xml" -H "Authorization: 73034021-THIS-IS-SAMPLE-KEY" 'http://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/'
```

```
var client = new RestClient("https://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/");  
var request = new RestRequest(Method.GET);  
request.AddHeader("Authorization", "73034021-THIS-IS-SAMPLE-KEY");  
IRestResponse response = client.Execute(request);
```

```
<?php  
$request = new HttpRequest();  
$request->setUrl('https://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/');  
$request->setMethod(HTTP_METH_GET);  
$request->setHeaders(array(  
  'Authorization' => '73034021-THIS-IS-SAMPLE-KEY'  
));  
try {  
  $response = $request->send();  
  echo $response->getBody();  
} catch (HttpException $ex) {  
  echo $ex;  
}  
?>
```

```
import requests  
url = 'https://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/'  
headers = {'Authorization' : '73034021-THIS-IS-SAMPLE-KEY'}  
response = requests.get(url, headers=headers)
```

```
const https = require('https');  
var options = {  
  "method": "GET",  
  "hostname": "flatfiles.coinapi.io",  
  "path": "/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/",  
  "headers": {'Authorization': '73034021-THIS-IS-SAMPLE-KEY'}  
};  
var request = https.request(options, function (response) {  
  var chunks = [];  
  response.on("data", function (chunk) {  
    chunks.push(chunk);  
  });  
});  
request.end();
```

```
import (  
  "gopkg.in/resty.v0"  
)  
func main()   
{  
    resp, err := resty.R().  
      SetHeader("Authorization", "73034021-THIS-IS-SAMPLE-KEY").  
      Get("https://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/")  
}
```

```
require 'uri'  
require 'net/http'  
url = URI("https://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/")  
http = Net::HTTP.new(url.host, url.port)  
request = Net::HTTP::Get.new(url)  
request["Authorization"] = '73034021-THIS-IS-SAMPLE-KEY'  
response = http.request(request)  
puts response.read_body
```

```
OkHttpClient client = new OkHttpClient();  
Request request = new Request.Builder()  
  .url("https://s3.flatfiles.coinapi.io/bucket/?prefix=T-LIMITBOOK_FULL/D-20220904/")  
  .post(body)  
  .addHeader("Authorization", "73034021-THIS-IS-SAMPLE-KEY")  
  .build();  
Response response = client.newCall(request).execute();
```

#### Example Response[​](/flat-files-api/s3-api/#example-response "Direct link to Example Response")

```
<ListBucketResult xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <ContentLength>0</ContentLength>  
    <HttpStatusCode>OK</HttpStatusCode>  
    <IsTruncated>false</IsTruncated>  
    <Contents>  
        <Key>T-LIMITBOOK_FULL/D-20220904/E-BINANCE/</Key>  
        <LastModified>2023-05-31T00:25:20.22186Z</LastModified>  
        <Size>36135124</Size>  
    </Contents>  
    <!-- Additional <Contents> elements -->  
    <MaxKeys>0</MaxKeys>  
    <KeyCount>0</KeyCount>  
</ListBucketResult>
```

### Download Object GET[​](/flat-files-api/s3-api/#download-object-get "Direct link to download-object-get")

This operation allows you to retrieve a specific object (file) from the bucket. It corresponds to the [GetObject](https://docs.aws.amazon.com/AmazonS3/latest/API/API_GetObject.html) operation in Amazon S3.

#### Usage Notes[​](/flat-files-api/s3-api/#usage-notes-1 "Direct link to Usage Notes")

* This operation is streamlined for the Flat Files S3 API and may not support all parameters from the Amazon S3 GetObject operation.
* Multi-part download operations are not supported.
* For optimal performance, adhere to the request syntax provided in the HTTP Request section.

#### HTTP Request[​](/flat-files-api/s3-api/#http-request-1 "Direct link to HTTP Request")

```
GET /bucket/{Key}
```

#### URL Parameters[​](/flat-files-api/s3-api/#url-parameters-1 "Direct link to URL Parameters")

| Parameter | Type | Description |
| --- | --- | --- |
| Key | string | The key (path) of the object to retrieve |

Error Handling[​](/flat-files-api/s3-api/#error-handling "Direct link to Error Handling")
-----------------------------------------------------------------------------------------

The Flat Files S3 API uses standard HTTP status codes and provides detailed error messages in XML format, consistent with Amazon S3 REST Error Responses.

### Error Response Format[​](/flat-files-api/s3-api/#error-response-format "Direct link to Error Response Format")

```
<?xml version="1.0" encoding="UTF-8"?>  
<Error>  
  <Code>ErrorCode</Code>  
  <Message>Error message description</Message>  
  <Resource>/bucket/object-key</Resource>   
  <RequestId>UniqueRequestIdentifier</RequestId>  
</Error>
```

### Common Error Codes[​](/flat-files-api/s3-api/#common-error-codes "Direct link to Common Error Codes")

| Error Code | HTTP Status | Meaning |
| --- | --- | --- |
| 400 | Bad Request | The request was invalid or cannot be served |
| 401 | Unauthorized | Authentication failed or user doesn't have permissions for the requested operation |
| 403 | Forbidden | Access denied due to insufficient privileges |
| 550 | No Data | The requested item is not available |

info

Best Practice: Implement robust error handling in your application. Store all error messages along with the corresponding request data for troubleshooting and analysis.

Compatible Software and Tools[​](/flat-files-api/s3-api/#compatible-software-and-tools "Direct link to Compatible Software and Tools")
--------------------------------------------------------------------------------------------------------------------------------------

The Flat Files S3 API is designed to work with a wide range of S3-compatible software and tools. Here are some popular options:

### AWS CLI[​](/flat-files-api/s3-api/#aws-cli "Direct link to AWS CLI")

The AWS Command Line Interface (CLI) is a unified tool to manage your AWS services, including S3-compatible storage like our Flat Files S3 API.

#### Installation[​](/flat-files-api/s3-api/#installation "Direct link to Installation")

* python
* linux
* macos
* windows

```
pip install awscli
```

```
sudo apt-get install awscli
```

```
brew install awscli
```

```
Download and install the AWS CLI from https://aws.amazon.com/cli/
```

#### Configuration[​](/flat-files-api/s3-api/#configuration "Direct link to Configuration")

1. Open a terminal or command prompt.
2. Run:

   ```
   aws configure
   ```
3. Enter the following information when prompted:

   ```
   AWS Access Key ID: 73034021-THIS-IS-SAMPLE-KEY  
   AWS Secret Access Key: coinapi  
   Default region name: us-east-1  
   Default output format: [Leave blank]
   ```

#### Usage Examples[​](/flat-files-api/s3-api/#usage-examples "Direct link to Usage Examples")

1. List buckets:

   ```
   aws --endpoint-url http://s3.flatfiles.coinapi.io s3 ls s3://coinapi
   ```
2. Download a file:

   ```
   aws --endpoint-url http://s3.flatfiles.coinapi.io s3 cp s3://coinapi/T-LIMITBOOK_FULL/D-20220904/E-COINBASE/IDDI-27576+SC-COINBASE_SPOT_BTC_USD+S-BTC__002DUSD.csv.gz /local/path/
   ```

### S3 Browser[​](/flat-files-api/s3-api/#s3-browser "Direct link to S3 Browser")

S3 Browser is a popular Windows client for Amazon S3 and compatible services.

#### Configuration Steps[​](/flat-files-api/s3-api/#configuration-steps "Direct link to Configuration Steps")

1. Download and install S3 Browser from <https://s3browser.com>
2. Launch S3 Browser
3. Add a new account:
   * Click "File" > "Add New Account"
   * Enter account details:
     + Account Name: CoinAPI Flat Files
     + Access Key ID: 73034021-THIS-IS-SAMPLE-KEY
     + Secret Access Key: coinapi
     + REST Endpoint: <http://s3.flatfiles.coinapi.io>
   * Choose HTTP or HTTPS for the connection type
   * Test the connection
   * Save the account settings
4. Browse the S3 buckets in the left sidebar

Best Practices and Optimization[​](/flat-files-api/s3-api/#best-practices-and-optimization "Direct link to Best Practices and Optimization")
--------------------------------------------------------------------------------------------------------------------------------------------

To make the most of the Flat Files S3 API, consider the following best practices:

1. Use efficient querying: Utilize the `prefix` parameter when listing objects to narrow down results.
2. Implement robust error handling: Always check for and appropriately handle error responses.
3. Use HTTPS for production: Ensure data security by using the HTTPS endpoint in production environments.
4. Optimize data retrieval: Download only the data you need, using date ranges and specific symbol filters when available.
5. Cache frequently accessed data: Implement local caching to reduce API calls for repetitive queries.
6. Monitor your usage: Keep track of your API usage to stay within rate limits and optimize costs.

Conclusion[​](/flat-files-api/s3-api/#conclusion "Direct link to Conclusion")
-----------------------------------------------------------------------------

The Flat Files S3 API provides a powerful and flexible way to access historical cryptocurrency market data. By leveraging S3 compatibility, it allows for easy integration with existing tools and workflows while offering optimized performance for large-scale data retrieval.

For further assistance, feature requests, or to report issues, please contact our support team.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Trades Dataset](/flat-files-api/snowflake/trades)[Next

Introduction](/flat-files-api/s3-api/)

* [Introduction](/flat-files-api/s3-api/#introduction)
* [General Overview](/flat-files-api/s3-api/#general-overview)
  + [What is Flat Files S3 API?](/flat-files-api/s3-api/#what-is-flat-files-s3-api)
  + [Key Features](/flat-files-api/s3-api/#key-features)
* [API Specifications](/flat-files-api/s3-api/#api-specifications)
  + [Implemented Standards](/flat-files-api/s3-api/#implemented-standards)
  + [Endpoints](/flat-files-api/s3-api/#endpoints)
  + [HTTP Requests](/flat-files-api/s3-api/#http-requests)
* [Authentication](/flat-files-api/s3-api/#authentication)
* [Supported Operations](/flat-files-api/s3-api/#supported-operations)
  + [List Objects GET](/flat-files-api/s3-api/#list-objects-get)
  + [Download Object GET](/flat-files-api/s3-api/#download-object-get)
* [Error Handling](/flat-files-api/s3-api/#error-handling)
  + [Error Response Format](/flat-files-api/s3-api/#error-response-format)
  + [Common Error Codes](/flat-files-api/s3-api/#common-error-codes)
* [Compatible Software and Tools](/flat-files-api/s3-api/#compatible-software-and-tools)
  + [AWS CLI](/flat-files-api/s3-api/#aws-cli)
  + [S3 Browser](/flat-files-api/s3-api/#s3-browser)
* [Best Practices and Optimization](/flat-files-api/s3-api/#best-practices-and-optimization)
* [Conclusion](/flat-files-api/s3-api/#conclusion)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.