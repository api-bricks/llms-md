Authentication < S3 API < Flat Files | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/s3-api/authentication)

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

* [S3 API](/flat-files-api/s3-api/)
* Authentication

On this page

Authentication for Flat Files S3 API
====================================

The Flat Files S3 API uses S3-compatible authentication methods. This allows you to use existing S3 tools and libraries to access our data securely.

Authentication Methods[​](/flat-files-api/s3-api/authentication#authentication-methods "Direct link to Authentication Methods")
-------------------------------------------------------------------------------------------------------------------------------

1. **API Key as Access Key ID**: Your CoinAPI key serves as the Access Key ID.
2. **Static Secret Key**: Use "coinapi" as the Secret Access Key.
3. **AWS Signature**: Requests should be signed using AWS Signature Version 2 or 4.

Configuration Examples[​](/flat-files-api/s3-api/authentication#configuration-examples "Direct link to Configuration Examples")
-------------------------------------------------------------------------------------------------------------------------------

### AWS CLI[​](/flat-files-api/s3-api/authentication#aws-cli "Direct link to AWS CLI")

Configure the AWS CLI with the following command:

```
aws configure
```

Enter the following information when prompted:

```
AWS Access Key ID: YOUR_COINAPI_KEY  
AWS Secret Access Key: coinapi  
Default region name: us-east-1  
Default output format: json
```

**Keep in mind for AWS CLI:**

1. Make sure that your AWS CLI is updated to the latest version. Outdated versions can cause issues when running the API.
2. AWS CLI has a default value of 8 MB for multipart\_threshold which can result to multiple API Request used. You may edit this threshold on your system to minimize the consumption of API requests.

### S3 Browser[​](/flat-files-api/s3-api/authentication#s3-browser "Direct link to S3 Browser")

In S3 Browser, create a new account with these settings:

* Account Name: CoinAPI Flat Files
* Access Key ID: YOUR\_COINAPI\_KEY
* Secret Access Key: coinapi
* Rest Endpoint: <https://s3.flatfiles.coinapi.io>

### SDK Usage[​](/flat-files-api/s3-api/authentication#sdk-usage "Direct link to SDK Usage")

When using S3 SDKs, configure the client as follows:

```
import boto3  
  
s3 = boto3.client('s3',  
    aws_access_key_id='YOUR_COINAPI_KEY',  
    aws_secret_access_key='coinapi',  
    endpoint_url='http://s3.flatfiles.coinapi.io'  
)
```

Remember to replace 'YOUR\_COINAPI\_KEY' with your actual CoinAPI key in all examples.

AWS Signature Authentication[​](/flat-files-api/s3-api/authentication#aws-signature-authentication "Direct link to AWS Signature Authentication")
-------------------------------------------------------------------------------------------------------------------------------------------------

### AWS Signature Version 2[​](/flat-files-api/s3-api/authentication#aws-signature-version-2 "Direct link to AWS Signature Version 2")

For this method of authorization, please put the API Key in both the `Access Key ID` and `Secret Access Key` fields.

### AWS Signature Version 4[​](/flat-files-api/s3-api/authentication#aws-signature-version-4 "Direct link to AWS Signature Version 4")

Amazon S3 uses the `Authorization` request header to provide authorization information. The value for this header must follow a specific pattern described as [AWS Signature Version 4](https://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-auth-using-authorization-header.html).

The example below shows the Authorization header value compliant with AWS Signature Version 4.

Please note that the Credential string contains our `apikey` as access-key-id.
Assuming that your API key is `73034021-THIS-IS-SAMPLE-KEY`, then the authorization header you should send to us will look like:

```
Authorization: AWS4-HMAC-SHA256  
Credential=73034021-THIS-IS-SAMPLE-KEY/20211203/us-east-1/s3/aws4_request,  
SignedHeaders=host;  
Signature=65e655c69da9906ac6076a28f75d9e4947aaed3be1f419757a3a84e24662673d
```

Although AWS Signature Version 4 is very strict about each of the signature components, our API takes only our `apikey` value into account.

Security Best Practices[​](/flat-files-api/s3-api/authentication#security-best-practices "Direct link to Security Best Practices")
----------------------------------------------------------------------------------------------------------------------------------

1. Keep your API key confidential.
2. Use HTTPS endpoints in production environments.
3. Regularly rotate your API keys.
4. Use the principle of least privilege when setting up IAM-like policies.

For any questions or support needs regarding authentication, please contact our support team.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/flat-files-api/s3-api/)[Next

SDK Guide](/flat-files-api/s3-api/sdk)

* [Authentication Methods](/flat-files-api/s3-api/authentication#authentication-methods)
* [Configuration Examples](/flat-files-api/s3-api/authentication#configuration-examples)
  + [AWS CLI](/flat-files-api/s3-api/authentication#aws-cli)
  + [S3 Browser](/flat-files-api/s3-api/authentication#s3-browser)
  + [SDK Usage](/flat-files-api/s3-api/authentication#sdk-usage)
* [AWS Signature Authentication](/flat-files-api/s3-api/authentication#aws-signature-authentication)
  + [AWS Signature Version 2](/flat-files-api/s3-api/authentication#aws-signature-version-2)
  + [AWS Signature Version 4](/flat-files-api/s3-api/authentication#aws-signature-version-4)
* [Security Best Practices](/flat-files-api/s3-api/authentication#security-best-practices)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.