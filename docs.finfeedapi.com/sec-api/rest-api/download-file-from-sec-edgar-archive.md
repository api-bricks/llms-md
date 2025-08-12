Download file from SEC EDGAR archive | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [SEC Filings API](/sec-api/)
* [Authentication](/sec-api/authentication)
* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)

  + [Introduction](/sec-api/rest-api/finfeedapi-sec-rest-api)
  + [File Download](/sec-api/rest-api/download-file-from-sec-edgar-archive)

    - [Download file from SEC EDGAR archive](/sec-api/rest-api/download-file-from-sec-edgar-archive)
  + [Content Extraction](/sec-api/rest-api/extract-and-classify-sec-filing-content)
  + [Filing Metadata](/sec-api/rest-api/query-sec-filing-metadata)
  + [Full Text Search](/sec-api/rest-api/full-text-search-of-sec-filing-documents)
  + [XBRL Conversion](/sec-api/rest-api/convert-xbrl-data-to-json-format)
* [Websocket API](/sec-api/websocket/)
* [JSON RPC](/sec-api/jsonrpc-api)

* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)
* File Download
* Download file from SEC EDGAR archive

Download file from SEC EDGAR archive
====================================

```
GET

/v1/download
------------
```

Downloads a specific file from the SEC EDGAR archive using the accession number and filename.
The file is streamed directly from the SEC servers to the client.

### Accession Number Format[​](/sec-api/rest-api/download-file-from-sec-edgar-archive#accession-number-format "Direct link to Accession Number Format")

Accession numbers must be in the format: 0000000000-00-000000 (10 digits, dash, 2 digits, dash, 6 digits)

### File Name Examples[​](/sec-api/rest-api/download-file-from-sec-edgar-archive#file-name-examples "Direct link to File Name Examples")

* Primary documents: `d123456d10k.htm`, `d789012d8k.htm`
* XBRL files: `d123456d10k_htm.xml`, `FilingSummary.xml`
* Exhibits: `d123456dexhibit99.htm`, `d123456dex101.htm`

### File Types[​](/sec-api/rest-api/download-file-from-sec-edgar-archive#file-types "Direct link to File Types")

The endpoint supports downloading various file types from SEC filings:

* HTML documents (.htm, .html)
* XBRL files (.xml, .xsd)
* Text files (.txt)
* PDF files (.pdf)
* Other document formats as submitted to SEC

tip

You can find available filenames for a specific filing using the `/v1/filings` endpoint first

warning

This endpoint streams files directly from the SEC. Large files may take longer to download.

Request[​](/sec-api/rest-api/download-file-from-sec-edgar-archive#request "Direct link to Request")
---------------------------------------------------------------------------------------------------

### Query Parameters

**accession\_no** stringrequired

**Possible values:** Value must match regular expression `^\d{10}-\d{2}-\d{6}$`

SEC filing accession number in format: 0000000000-00-000000

**file\_name** stringrequired

Name of the file to download from the filing

Responses[​](/sec-api/rest-api/download-file-from-sec-edgar-archive#responses "Direct link to Responses")
---------------------------------------------------------------------------------------------------------

* 200
* 400
* 404
* 500

File downloaded successfully

* application/octet-stream
* text/html
* application/xml
* text/plain
* application/pdf

* Schema

**Schema**

any

* Schema

**Schema**

any

* Schema

**Schema**

any

* Schema

**Schema**

any

* Schema

**Schema**

any

Invalid request parameters

* application/octet-stream
* application/json

* Schema
* Example (from schema)

**Schema**

**type** stringnullable

**title** stringnullable

**status** int32nullable

**detail** stringnullable

**instance** stringnullable

**errors**

object

nullable

**property name\***

string[]

nullable

* Array [

string

* ]

**property name\*** any

```
{  
  "type": "string",  
  "title": "string",  
  "status": 0,  
  "detail": "string",  
  "instance": "string",  
  "errors": {}  
}
```

* Schema
* Example (from schema)

**Schema**

**type** stringnullable

**title** stringnullable

**status** int32nullable

**detail** stringnullable

**instance** stringnullable

**errors**

object

nullable

**property name\***

string[]

nullable

* Array [

string

* ]

**property name\*** any

```
{  
  "type": "string",  
  "title": "string",  
  "status": 0,  
  "detail": "string",  
  "instance": "string",  
  "errors": {}  
}
```

Filing or file not found

* application/octet-stream
* application/json

* Schema
* Example (from schema)

**Schema**

**type** stringnullable

**title** stringnullable

**status** int32nullable

**detail** stringnullable

**instance** stringnullable

**property name\*** any

```
{  
  "type": "string",  
  "title": "string",  
  "status": 0,  
  "detail": "string",  
  "instance": "string"  
}
```

* Schema
* Example (from schema)

**Schema**

**type** stringnullable

**title** stringnullable

**status** int32nullable

**detail** stringnullable

**instance** stringnullable

**property name\*** any

```
{  
  "type": "string",  
  "title": "string",  
  "status": 0,  
  "detail": "string",  
  "instance": "string"  
}
```

Server error

* application/octet-stream
* application/json

* Schema
* Example (from schema)

**Schema**

**type** stringnullable

**title** stringnullable

**status** int32nullable

**detail** stringnullable

**instance** stringnullable

**property name\*** any

```
{  
  "type": "string",  
  "title": "string",  
  "status": 0,  
  "detail": "string",  
  "instance": "string"  
}
```

* Schema
* Example (from schema)

**Schema**

**type** stringnullable

**title** stringnullable

**status** int32nullable

**detail** stringnullable

**instance** stringnullable

**property name\*** any

```
{  
  "type": "string",  
  "title": "string",  
  "status": 0,  
  "detail": "string",  
  "instance": "string"  
}
```

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Introduction](/sec-api/rest-api/finfeedapi-sec-rest-api)[Next

Extract and classify SEC filing content](/sec-api/rest-api/extract-and-classify-sec-filing-content)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.