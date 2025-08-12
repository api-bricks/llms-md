Extract specific item content from SEC filing | FinFeedAPI.com Documentation




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
  + [Content Extraction](/sec-api/rest-api/extract-and-classify-sec-filing-content)

    - [Extract and classify SEC filing content](/sec-api/rest-api/extract-and-classify-sec-filing-content)
    - [Extract specific item content from SEC filing](/sec-api/rest-api/extract-specific-item-content-from-sec-filing)
  + [Filing Metadata](/sec-api/rest-api/query-sec-filing-metadata)
  + [Full Text Search](/sec-api/rest-api/full-text-search-of-sec-filing-documents)
  + [XBRL Conversion](/sec-api/rest-api/convert-xbrl-data-to-json-format)
* [Websocket API](/sec-api/websocket/)
* [JSON RPC](/sec-api/jsonrpc-api)

* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)
* Content Extraction
* Extract specific item content from SEC filing

Extract specific item content from SEC filing
=============================================

```
GET

/v1/extractor/item
------------------
```

Retrieves filing content from the EDGAR database and returns only the text content of the specified item number.

### Item Number Format[​](/sec-api/rest-api/extract-specific-item-content-from-sec-filing#item-number-format "Direct link to Item Number Format")

| Form Type | Item Format Examples |
| --- | --- |
| 8-K | 1.01, 2.01, 7.01 |
| 10-K | 1, 2, 3 |
| 10-K/10-Q | PartI 1, PartII 2 |

tip

For best results, ensure the item number matches exactly with the filing's structure.

Request[​](/sec-api/rest-api/extract-specific-item-content-from-sec-filing#request "Direct link to Request")
------------------------------------------------------------------------------------------------------------

### Query Parameters

**accession\_number** stringrequired

The SEC filing accession number used to retrieve the filing from EDGAR database.

**item\_number** stringrequired

The specific item number to extract (e.g., "1.01", "2.01", "7.01").

**type** DTO.ExtractorType

**Possible values:** [`text`, `html`]

Result type (text or html, default: text)

Responses[​](/sec-api/rest-api/extract-specific-item-content-from-sec-filing#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------------------

* 200
* 400
* 404
* 500

Successful extraction

* application/json

* Schema

**Schema**

string

Invalid request

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

Filing or item not found

Server error

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

Loading...

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Extract and classify SEC filing content](/sec-api/rest-api/extract-and-classify-sec-filing-content)[Next

Query SEC filing metadata](/sec-api/rest-api/query-sec-filing-metadata)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.