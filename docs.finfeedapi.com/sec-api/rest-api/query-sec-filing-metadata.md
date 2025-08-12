Query SEC filing metadata | FinFeedAPI.com Documentation




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

    - [Query SEC filing metadata](/sec-api/rest-api/query-sec-filing-metadata)
  + [Full Text Search](/sec-api/rest-api/full-text-search-of-sec-filing-documents)
  + [XBRL Conversion](/sec-api/rest-api/convert-xbrl-data-to-json-format)
* [Websocket API](/sec-api/websocket/)
* [JSON RPC](/sec-api/jsonrpc-api)

* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)
* Filing Metadata
* Query SEC filing metadata

Query SEC filing metadata
=========================

```
GET

/v1/filings
-----------
```

Retrieves metadata for SEC filings based on various filter criteria with pagination and sorting support.

### Available Sort Fields[​](/sec-api/rest-api/query-sec-filing-metadata#available-sort-fields "Direct link to Available Sort Fields")

| Field Name | Description |
| --- | --- |
| AccessionNumber | SEC filing accession number |
| FilingDate | Date when filing was submitted |
| AcceptanceDateTime | Date and time of filing acceptance |
| ReportDate | Date of the report |
| Size | Size of the filing document |

### Date Format[​](/sec-api/rest-api/query-sec-filing-metadata#date-format "Direct link to Date Format")

All dates must be provided in YYYY-MM-DD format

### Form Types[​](/sec-api/rest-api/query-sec-filing-metadata#form-types "Direct link to Form Types")

Form types can be provided as comma-separated values, e.g.: "10-K,8-K,10-Q"

tip

For optimal performance, use date ranges and form types to narrow down your search

Request[​](/sec-api/rest-api/query-sec-filing-metadata#request "Direct link to Request")
----------------------------------------------------------------------------------------

### Query Parameters

**cik** int64

Filter by Central Index Key (CIK)

**ticker** string

Filter by stock ticker symbol

**form\_type** string

Filter by form type(s) (e.g., "10-K", "8-K"). Multiple values can be comma-separated

**filling\_date\_start** string

**Possible values:** Value must match regular expression `^\d{4}-\d{2}-\d{2}$`

Filter by filling date start (inclusive), format YYYY-MM-DD

**filling\_date\_end** string

**Possible values:** Value must match regular expression `^\d{4}-\d{2}-\d{2}$`

Filter by filling date end (inclusive), format YYYY-MM-DD

**report\_date\_start** string

**Possible values:** Value must match regular expression `^\d{4}-\d{2}-\d{2}$`

Filter by report date start (inclusive), format YYYY-MM-DD

**report\_date\_end** string

**Possible values:** Value must match regular expression `^\d{4}-\d{2}-\d{2}$`

Filter by report date end (inclusive), format YYYY-MM-DD

**items\_contain** string

Filter filings where the 'Items' field contains the specified text

**page\_size** int32

**Possible values:** `>= 1` and `<= 200`

Number of results per page (default: 50, max: 200)

**page\_number** int32

**Possible values:** `>= 1` and `<= 2147483647`

Page number to retrieve (default: 1)

**sort\_by** DTO.FilingSortBy

**Possible values:** [`AccessionNumber`, `FilingDate`, `ReportDate`, `AcceptanceDateTime`, `Size`]

Field to sort results by (default: AccessionNumber)

**sort\_order** string

**Possible values:** Value must match regular expression `^(asc|desc)$`

**Default value:** `desc`

Sort order (asc or desc, default: desc)

Responses[​](/sec-api/rest-api/query-sec-filing-metadata#responses "Direct link to Responses")
----------------------------------------------------------------------------------------------

* 200
* 400
* 500

Successful operation

* application/json

* Schema
* Example (from schema)
* Example Filing Metadata

**Schema**

* Array [

**cik** int64

**accession\_number** stringnullable

**filing\_date** date

**report\_date** datenullable

**acceptance\_date\_time** date-timenullable

**act** stringnullable

**form** stringnullable

**file\_number** stringnullable

**film\_number** stringnullable

**items** stringnullable

**core\_type** stringnullable

**size** int32nullable

**is\_xbrl** booleannullable

**is\_inline\_xbrl** booleannullable

**primary\_document** stringnullable

**primary\_doc\_description** stringnullable

**source\_file** stringnullable

* ]

```
[  
  {  
    "cik": 0,  
    "accession_number": "string",  
    "filing_date": "2025-08-12",  
    "report_date": "2025-08-12",  
    "acceptance_date_time": "2025-08-12T06:08:07.063Z",  
    "act": "string",  
    "form": "string",  
    "file_number": "string",  
    "film_number": "string",  
    "items": "string",  
    "core_type": "string",  
    "size": 0,  
    "is_xbrl": true,  
    "is_inline_xbrl": true,  
    "primary_document": "string",  
    "primary_doc_description": "string",  
    "source_file": "string"  
  }  
]
```

```
{  
  "cik": 1234567890,  
  "accession_number": "0001140361-21-012345",  
  "filing_date": "2021-03-15",  
  "report_date": "2020-12-31",  
  "acceptance_date_time": "2021-03-15T16:30:00.0000000Z",  
  "act": "34",  
  "form": "10-K",  
  "file_number": "001-12345",  
  "film_number": "21654321",  
  "items": "1,1A,2",  
  "core_type": "10-K",  
  "size": 15000000,  
  "is_xbrl": true,  
  "is_inline_xbrl": true,  
  "primary_document": "form10k.htm",  
  "primary_doc_description": "Form 10-K Annual Report",  
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

Extract specific item content from SEC filing](/sec-api/rest-api/extract-specific-item-content-from-sec-filing)[Next

Full-text search of SEC filing documents](/sec-api/rest-api/full-text-search-of-sec-filing-documents)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.