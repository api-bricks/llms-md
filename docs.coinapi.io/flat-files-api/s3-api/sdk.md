SDK Guide < S3 API < Flat Files | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/flat-files-api/s3-api/sdk)

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
* SDK Guide

On this page

S3 Compatible Flat Files SDK Guide
==================================

This guide provides information on available SDKs for integrating with S3 compatible Flat Files, along with installation and configuration examples for various programming languages.

Available SDKs[​](/flat-files-api/s3-api/sdk#available-sdks "Direct link to Available SDKs")
--------------------------------------------------------------------------------------------

* JavaScript (Node.js)
* Python
* Java
* .NET (C#)
* Ruby
* PHP
* Go

Install the AWS SDK for JavaScript:

```
npm install @aws-sdk/client-s3
```

Configure the client:

```
import { S3 } from "@aws-sdk/client-s3";  
  
const s3Client = new S3({  
    endpoint: "https://s3.flatfiles.coinapi.io",  
    region: "us-east-1",  
    credentials: {  
        accessKeyId: process.env.COINAPI_KEY,  
        secretAccessKey: "coinapi"  
    }  
});  
  
export { s3Client };
```

For more information, refer to the [JavaScript SDK documentation](https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/clients/client-s3/).

Install the Boto3 SDK:

```
pip install boto3
```

Configure the client:

```
import boto3  
  
client = boto3.client('s3',  
                      region_name='us-east-1',  
                      endpoint_url='https://s3.flatfiles.coinapi.io',  
                      aws_access_key_id='your_coinapi_key',  
                      aws_secret_access_key='coinapi')
```

For more information, refer to the [Python SDK documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/s3.html).

Add Maven dependency for AWS SDK for Java:

```
<dependency>  
    <groupId>com.amazonaws</groupId>  
    <artifactId>aws-java-sdk-s3</artifactId>  
    <version>1.12.201</version>  
</dependency>
```

Configure the client:

```
import com.amazonaws.auth.AWSStaticCredentialsProvider;  
import com.amazonaws.auth.BasicAWSCredentials;  
import com.amazonaws.client.builder.AwsClientBuilder;  
import com.amazonaws.services.s3.AmazonS3;  
import com.amazonaws.services.s3.AmazonS3ClientBuilder;  
  
AmazonS3 s3Client = AmazonS3ClientBuilder.standard()  
        .withEndpointConfiguration(new AwsClientBuilder.EndpointConfiguration("https://s3.flatfiles.coinapi.io", "us-east-1"))  
        .withCredentials(new AWSStaticCredentialsProvider(new BasicAWSCredentials("your_coinapi_key", "coinapi")))  
        .build();
```

For more information, refer to the [Java SDK documentation](https://docs.aws.amazon.com/sdk-for-java/v1/developer-guide/examples-s3.html).

Install the AWS SDK for .NET:

```
Install-Package AWSSDK.S3
```

Configure the client:

```
using Amazon.S3;  
using Amazon.S3.Model;  
using Amazon.Runtime;  
  
var client = new AmazonS3Client(new BasicAWSCredentials("your_coinapi_key", "coinapi"), new AmazonS3Config  
{  
    ServiceURL = "https://s3.flatfiles.coinapi.io",  
    AuthenticationRegion = "us-east-1"  
});
```

For more information, refer to the [.NET SDK documentation](https://docs.aws.amazon.com/sdk-for-net/v3/developer-guide/s3-apis-intro.html).

Install the AWS SDK for Ruby:

```
gem install aws-sdk-s3
```

Configure the client:

```
require 'aws-sdk-s3'  
  
s3 = Aws::S3::Client.new(  
  region: 'us-east-1',  
  endpoint: 'https://s3.flatfiles.coinapi.io',  
  access_key_id: 'your_coinapi_key',  
  secret_access_key: 'coinapi'  
)
```

For more information, refer to the [Ruby SDK documentation](https://docs.aws.amazon.com/sdk-for-ruby/v3/api/Aws/S3/Client.html).

Install the AWS SDK for PHP using Composer:

```
composer require aws/aws-sdk-php
```

Configure the client:

```
require 'vendor/autoload.php';  
  
use Aws\S3\S3Client;  
  
$s3Client = new S3Client([  
    'version' => 'latest',  
    'region'  => 'us-east-1',  
    'endpoint' => 'https://s3.flatfiles.coinapi.io',  
    'credentials' => [  
        'key'    => 'your_coinapi_key',  
        'secret' => 'coinapi',  
    ],  
]);
```

For more information, refer to the [PHP SDK documentation](https://docs.aws.amazon.com/sdk-for-php/v3/developer-guide/s3-examples.html).

Install the AWS SDK for Go:

```
go get -u github.com/aws/aws-sdk-go
```

Configure the client:

```
package main  
  
import (  
    "github.com/aws/aws-sdk-go/aws"  
    "github.com/aws/aws-sdk-go/aws/credentials"  
    "github.com/aws/aws-sdk-go/aws/session"  
    "github.com/aws/aws-sdk-go/service/s3"  
)  
  
func main() {  
    sess, _ := session.NewSession(&aws.Config{  
        Region:      aws.String("us-east-1"),  
        Endpoint:    aws.String("https://s3.flatfiles.coinapi.io"),  
        Credentials: credentials.NewStaticCredentials("your_coinapi_key", "coinapi", ""),  
    })  
  
    svc := s3.New(sess)  
}
```

For more information, refer to the [Go SDK documentation](https://docs.aws.amazon.com/sdk-for-go/api/service/s3/).

Additional Languages[​](/flat-files-api/s3-api/sdk#additional-languages "Direct link to Additional Languages")
--------------------------------------------------------------------------------------------------------------

For other programming languages such as Swift, Rust, and SAP ABAP, please refer to their respective AWS SDK documentation for S3 integration:

* [Swift SDK](https://github.com/swift-aws/aws-sdk-swift)
* [Rust SDK](https://github.com/awslabs/aws-sdk-rust)
* [SAP ABAP SDK](https://github.com/SAP/aws-abap-sdk)

Conclusion[​](/flat-files-api/s3-api/sdk#conclusion "Direct link to Conclusion")
--------------------------------------------------------------------------------

These SDKs support the S3 API, allowing you to interact with our S3-compatible Flat Files seamlessly. Follow the respective links for more detailed documentation and additional configurations.

When using these SDKs with our Flat Files:

* Replace `your_coinapi_key` with your actual CoinAPI key.
* Use `coinapi` as the secret access key.
* Set the endpoint URL to `https://s3.flatfiles.coinapi.io`.

For any issues or questions regarding SDK integration, please contact our support team.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Authentication](/flat-files-api/s3-api/authentication)[Next

Introduction](/flat-files-api/rest-api/push-api)

* [Available SDKs](/flat-files-api/s3-api/sdk#available-sdks)
* [Additional Languages](/flat-files-api/s3-api/sdk#additional-languages)
* [Conclusion](/flat-files-api/s3-api/sdk#conclusion)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.