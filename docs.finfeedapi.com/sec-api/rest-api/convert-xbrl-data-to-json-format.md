Convert XBRL data to JSON format | FinFeedAPI.com Documentation




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
  + [XBRL Conversion](/sec-api/rest-api/convert-xbrl-data-to-json-format)

    - [Convert XBRL data to JSON format](/sec-api/rest-api/convert-xbrl-data-to-json-format)
* [Websocket API](/sec-api/websocket/)
* [JSON RPC](/sec-api/jsonrpc-api)

* [REST API](/sec-api/rest-api/finfeedapi-sec-rest-api)
* XBRL Conversion
* Convert XBRL data to JSON format

Convert XBRL data to JSON format
================================

```
GET

/v1/xbrl-converter
------------------
```

Converts XBRL data to JSON format using one of three possible input methods.

### Input Methods[​](/sec-api/rest-api/convert-xbrl-data-to-json-format#input-methods "Direct link to Input Methods")

1. HTML URL (htm-url)

   * URL of the filing ending with .htm or .html
   * Both filing URLs and index page URLs are accepted
   * Example: <https://www.sec.gov/Archives/edgar/data/1318605/000156459021004599/tsla-10k_20201231.htm>
2. XBRL URL (xbrl-url)

   * URL of the XBRL file ending with .xml
   * Can be found in the dataFiles array from Query API
   * Example: <https://www.sec.gov/Archives/edgar/data/1318605/000156459021004599/tsla-10k_20201231_htm.xml>
3. Accession Number (accession-no)

   * The SEC filing accession number
   * Example: 0001564590-21-004599

note

Only one of the three parameters should be provided. If multiple parameters are provided, the priority order is:

1. htm-url
2. xbrl-url
3. accession-no

### Supported Filing Types[​](/sec-api/rest-api/convert-xbrl-data-to-json-format#supported-filing-types "Direct link to Supported Filing Types")

* Annual Reports (10-K)
* Quarterly Reports (10-Q)
* Current Reports (8-K)
* Registration Statements (S-1, S-3)
* Foreign Private Issuer Reports (20-F, 40-F)

### Response Format[​](/sec-api/rest-api/convert-xbrl-data-to-json-format#response-format "Direct link to Response Format")

The API returns a JSON object containing:

* Financial statements (Income Statement, Balance Sheet, Cash Flow Statement)
* Accounting policies and footnotes
* Company information
* Filing metadata

### Example Response[​](/sec-api/rest-api/convert-xbrl-data-to-json-format#example-response "Direct link to Example Response")

```
{  
  "StatementsOfIncome": {  
    "RevenueFromContractWithCustomerExcludingAssessedTax": [  
      {  
        "decimals": "-6",  
        "unitRef": "U_USD",  
        "period": {  
          "startDate": "2023-07-01",  
          "endDate": "2024-06-30"  
        },  
        "value": "245122000000"  
      }  
    ]  
  }  
}
```

Request[​](/sec-api/rest-api/convert-xbrl-data-to-json-format#request "Direct link to Request")
-----------------------------------------------------------------------------------------------

### Query Parameters

**htm-url** string

URL of the filing ending with .htm or .html

**xbrl-url** string

URL of the XBRL file ending with .xml

**accession-no** string

SEC filing accession number

Responses[​](/sec-api/rest-api/convert-xbrl-data-to-json-format#responses "Direct link to Responses")
-----------------------------------------------------------------------------------------------------

* 200
* 400
* 404
* 500

Successful conversion

* application/json

* Schema
* Example (from schema)
* Example XBRL Filing Extract

**Schema**

**property name\*** any

```
{}
```

```
{  
  "CoverPage": {  
    "DocumentType": "10-K",  
    "DocumentAnnualReport": "true",  
    "DocumentPeriodEndDate": "2020-09-26",  
    "DocumentTransitionReport": "false",  
    "EntityFileNumber": "001-36743",  
    "EntityRegistrantName": "Apple Inc.",  
    "EntityIncorporationStateCountryCode": "CA",  
    "EntityTaxIdentificationNumber": "94-2404110",  
    "EntityAddressAddressLine1": "One Apple Park Way",  
    "EntityAddressCityOrTown": "Cupertino",  
    "EntityAddressStateOrProvince": "CA",  
    "EntityAddressPostalZipCode": "95014",  
    "CityAreaCode": "408",  
    "LocalPhoneNumber": "996-1010",  
    "Security12bTitle": [  
      {  
        "period": {  
          "startDate": "2019-09-29",  
          "endDate": "2020-09-26"  
        },  
        "segment": {  
          "dimension": "us-gaap:StatementClassOfStockAxis",  
          "value": "us-gaap:CommonStockMember"  
        },  
        "value": "Common Stock, $0.00001 par value per share"  
      }  
    ],  
    "TradingSymbol": {  
      "period": {  
        "startDate": "2019-09-29",  
        "endDate": "2020-09-26"  
      },  
      "segment": {  
        "dimension": "us-gaap:StatementClassOfStockAxis",  
        "value": "us-gaap:CommonStockMember"  
      },  
      "value": "AAPL"  
    },  
    "NoTradingSymbolFlag": [  
      {  
        "period": {  
          "startDate": "2019-09-29",  
          "endDate": "2020-09-26"  
        },  
        "segment": {  
          "dimension": "us-gaap:StatementClassOfStockAxis",  
          "value": "aapl:A1.000NotesDue2022Member"  
        },  
        "value": "true"  
      }  
    ],  
    "SecurityExchangeName": [  
      {  
        "period": {  
          "startDate": "2019-09-29",  
          "endDate": "2020-09-26"  
        },  
        "segment": {  
          "dimension": "us-gaap:StatementClassOfStockAxis",  
          "value": "us-gaap:CommonStockMember"  
        },  
        "value": "NASDAQ"  
      }  
    ],  
    "EntityWellKnownSeasonedIssuer": "Yes",  
    "EntityVoluntaryFilers": "No",  
    "EntityCurrentReportingStatus": "Yes",  
    "EntityInteractiveDataCurrent": "Yes",  
    "EntityFilerCategory": "Large Accelerated Filer",  
    "EntitySmallBusiness": "false",  
    "EntityEmergingGrowthCompany": "false",  
    "IcfrAuditorAttestationFlag": "true",  
    "EntityShellCompany": "false",  
    "EntityPublicFloat": {  
      "decimals": "-6",  
      "unitRef": "usd",  
      "period": {  
        "instant": "2020-03-27"  
      },  
      "value": "1070633000000"  
    },  
    "EntityCommonStockSharesOutstanding": {  
      "decimals": "-3",  
      "unitRef": "shares",  
      "period": {  
        "instant": "2020-10-16"  
      },  
      "value": "17001802000"  
    },  
    "AmendmentFlag": "false",  
    "DocumentFiscalYearFocus": "2020",  
    "DocumentFiscalPeriodFocus": "FY",  
    "EntityCentralIndexKey": "0000320193",  
    "CurrentFiscalYearEndDate": "--09-26"  
  },  
  "StatementsOfIncome": {  
    "RevenueFromContractWithCustomerExcludingAssessedTax": [  
      {  
        "decimals": "-6",  
        "unitRef": "usd",  
        "period": {  
          "startDate": "2019-09-29",  
          "endDate": "2020-09-26"  
        },  
        "segment": {  
          "dimension": "srt:ProductOrServiceAxis",  
          "value": "us-gaap:ProductMember"  
        },  
        "value": "220747000000"  
      }  
    ],  
    "CostOfGoodsAndServicesSold": [],  
    "GrossProfit": [],  
    "ResearchAndDevelopmentExpense": [],  
    "SellingGeneralAndAdministrativeExpense": [],  
    "OperatingExpenses": [],  
    "OperatingIncomeLoss": [],  
    "NonoperatingIncomeExpense": [],  
    "IncomeLossFromContinuingOperationsBeforeIncomeTaxesExtraordinaryItemsNoncontrollingInterest": [],  
    "IncomeTaxExpenseBenefit": [],  
    "NetIncomeLoss": [],  
    "EarningsPerShareBasic": [],  
    "EarningsPerShareDiluted": [],  
    "WeightedAverageNumberOfSharesOutstandingBasic": [],  
    "WeightedAverageNumberOfDilutedSharesOutstanding": []  
  },  
  "StatementsOfComprehensiveIncome": {  
    "NetIncomeLoss": [],  
    "OtherComprehensiveIncomeLossForeignCurrencyTransactionAndTranslationAdjustmentNetOfTax": [],  
    "OtherComprehensiveIncomeLossDerivativeInstrumentGainLossbeforeReclassificationafterTax": {  
      "decimals": "-6",  
      "unitRef": "usd",  
      "period": {  
        "startDate": "2019-09-29",  
        "endDate": "2020-09-26"  
      },  
      "value": "79000000"  
    }  
  },  
  "BalanceSheets": {},  
  "BalanceSheetsParenthetical": {},  
  "StatementsOfShareholdersEquity": {},  
  "StatementsOfCashFlows": {},  
  "SummaryofSignificantAccountingPolicies": {},  
  "SummaryofSignificantAccountingPoliciesPolicies": {},  
  "SummaryofSignificantAccountingPoliciesTables": {},  
  "SummaryofSignificantAccountingPoliciesAdditionalInformationDetails": {},  
  "SummaryofSignificantAccountingPoliciesComputationofBasicandDilutedEarningsPerShareDetails": {},  
  "RevenueRecognition": {},  
  "RevenueRecognitionTables": {},  
  "RevenueRecognitionAdditionalInformationDetails": {},  
  "RevenueRecognitionDeferredRevenueExpectedTimingofRealizationDetails": {},  
  "RevenueRecognitionNetSalesDisaggregatedbySignificantProductsandServicesDetails": {},  
  "FinancialInstruments": {},  
  "FinancialInstrumentsTables": {},  
  "FinancialInstrumentsCashCashEquivalentsandMarketableSecuritiesDetails": {}  
}
```

Invalid request - check parameter format

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

Filing or XBRL data not found

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

Full-text search of SEC filing documents](/sec-api/rest-api/full-text-search-of-sec-filing-documents)[Next

Introduction](/sec-api/websocket/)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.