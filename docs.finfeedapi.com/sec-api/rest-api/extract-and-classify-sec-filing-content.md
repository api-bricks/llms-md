Extract and classify SEC filing content | FinFeedAPI.com Documentation




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
* Extract and classify SEC filing content

Extract and classify SEC filing content
=======================================

```
GET

/v1/extractor
-------------
```

Retrieves filing content from the EDGAR database and intelligently classifies it according to form type and item categories.

### Supported Form Types[​](/sec-api/rest-api/extract-and-classify-sec-filing-content#supported-form-types "Direct link to Supported Form Types")

| Form Type | Description |
| --- | --- |
| 8-K | Current report filing |
| 10-K | Annual report filing |
| 10-Q | Quarterly report filing |

### Content Classification[​](/sec-api/rest-api/extract-and-classify-sec-filing-content#content-classification "Direct link to Content Classification")

* 8-K forms: Content classified by item numbers (e.g., 1.01, 2.01)
* 10-K/10-Q forms: Items categorized by their respective part and item structure

note

Both HTML and plain text documents are supported for content extraction.

Request[​](/sec-api/rest-api/extract-and-classify-sec-filing-content#request "Direct link to Request")
------------------------------------------------------------------------------------------------------

### Query Parameters

**accession\_number** stringrequired

The SEC filing accession number used to retrieve the filing from EDGAR database.

**type** DTO.ExtractorType

**Possible values:** [`text`, `html`]

Result type (text or html, default: text)

Responses[​](/sec-api/rest-api/extract-and-classify-sec-filing-content#responses "Direct link to Responses")
------------------------------------------------------------------------------------------------------------

* 200
* 400
* 404
* 500

Successful extraction

* application/json

* Schema
* Example (from schema)
* Example Filing Extract

**Schema**

**property name\*** any

```
{}
```

```
{  
  "accession_number": "0001140361-21-012345",  
  "form_type": "10-K",  
  "items": [  
    {  
      "item_number": "Item 1",  
      "item_title": "Business",  
      "content": "Description of business operations..."  
    },  
    {  
      "item_number": "Item 1A",  
      "item_title": "Risk Factors",  
      "content": "Discussion of potential risks and uncertainties..."  
    },  
    {  
      "item_number": "Item 2",  
      "item_title": "Properties",  
      "content": "Description of company properties and facilities..."  
    }  
  ]  
}
```

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

Filing not found

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

Download file from SEC EDGAR archive](/sec-api/rest-api/download-file-from-sec-edgar-archive)[Next

Extract specific item content from SEC filing](/sec-api/rest-api/extract-specific-item-content-from-sec-filing)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.