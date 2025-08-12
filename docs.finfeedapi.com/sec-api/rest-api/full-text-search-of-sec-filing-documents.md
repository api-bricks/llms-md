Full-text search of SEC filing documents | FinFeedAPI.com Documentation




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
  + [Filing Metadata](/sec-api/rest-api/query-sec-filing-metadata)
  + [Full Text Search](/sec-api/rest-api/full-text-search-of-sec-filing-documents)

    - [Full-text search of SEC filing documents](/sec-api/rest-api/full-text-search-of-sec-filing-documents)
  + [XBRL Conversion](/sec-api/rest-api/convert-xbrl-data-to-json-format)
* [Websocket API](/sec-api/websocket/)
* [JSON RPC](/sec-api/jsonrpc-api)

* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)
* Full Text Search
* Full-text search of SEC filing documents

Full-text search of SEC filing documents
========================================

```
GET

/v1/full-text
-------------
```

Search across SEC filing documents with advanced filtering and sorting capabilities.

### Available Sort Fields[​](/sec-api/rest-api/full-text-search-of-sec-filing-documents#available-sort-fields "Direct link to Available Sort Fields")

| Field Name | Description |
| --- | --- |
| AccessionNumber | SEC filing accession number |
| FormType | Type of the filing document |
| FilingDate | Date when filing was submitted |
| CompanyName | Name of the company |
| CIK | Central Index Key |
| DocumentFilename | Name of the filing document |
| DocumentDescription | Description of the document |

### Search Options[​](/sec-api/rest-api/full-text-search-of-sec-filing-documents#search-options "Direct link to Search Options")

| Option | Description |
| --- | --- |
| text\_contains | Keywords that must appear in the document |
| text\_not\_contain | Keywords that must not appear in the document |

### Date Format[​](/sec-api/rest-api/full-text-search-of-sec-filing-documents#date-format "Direct link to Date Format")

All dates must be provided in YYYY-MM-DD format

tip

Use text\_contains and text\_not\_contain with multiple keywords separated by commas for more precise searches

note

The search is case-insensitive and supports partial word matches

Request[​](/sec-api/rest-api/full-text-search-of-sec-filing-documents#request "Direct link to Request")
-------------------------------------------------------------------------------------------------------

### Query Parameters

**form\_type** string

Filter by form type (e.g., "10-K", "8-K"). Multiple values can be comma-separated

**filling\_date\_start** string

**Possible values:** Value must match regular expression `^\d{4}-\d{2}-\d{2}$`

Filter by filling date start (inclusive), format YYYY-MM-DD

**filling\_date\_end** string

**Possible values:** Value must match regular expression `^\d{4}-\d{2}-\d{2}$`

Filter by filling date end (inclusive), format YYYY-MM-DD

**text\_contains** string

Keywords that the text must contain. Multiple values can be comma-separated

**text\_not\_contain** string

Keywords that the text must not contain. Multiple values can be comma-separated

**page\_size** int32

Number of results per page (default: 100)

**page\_number** int32

Page number to retrieve (default: 1)

**sort\_by** string

**Possible values:** Value must match regular expression `^(AccessionNumber|FormType|FilingDate|CompanyName|CIK|DocumentFilename|DocumentDescription)$`

**Default value:** `AccessionNumber`

Field to sort by (default: AccessionNumber)

**sort\_order** string

**Possible values:** Value must match regular expression `^(asc|desc)$`

**Default value:** `asc`

Sort order (asc or desc). Defaults to asc

Responses[​](/sec-api/rest-api/full-text-search-of-sec-filing-documents#responses "Direct link to Responses")
-------------------------------------------------------------------------------------------------------------

* 200
* 400
* 500

Successful operation

* application/json

* Schema
* Example (from schema)
* Example SEC Filing Result

**Schema**

* Array [

**accession\_number** stringnullable

**form\_type** stringnullable

**filing\_date** date

**company\_name** stringnullable

**cik** int64

**document\_filename** stringnullable

**document\_description** stringnullable

**source\_file** stringnullable

* ]

```
[  
  {  
    "accession_number": "string",  
    "form_type": "string",  
    "filing_date": "2025-08-12",  
    "company_name": "string",  
    "cik": 0,  
    "document_filename": "string",  
    "document_description": "string",  
    "source_file": "string"  
  }  
]
```

```
{  
  "accession_number": "0001140361-21-012345",  
  "form_type": "10-K",  
  "filing_date": "2021-03-15",  
  "company_name": "Example Corporation",  
  "cik": 1234567890,  
  "document_filename": "form10k.htm",  
  "document_description": "Form 10-K Annual Report",  
  "source_file": "edgar/data/1234567890/0001140361-21-012345.txt"  
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

Query SEC filing metadata](/sec-api/rest-api/query-sec-filing-metadata)[Next

Convert XBRL data to JSON format](/sec-api/rest-api/convert-xbrl-data-to-json-format)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.