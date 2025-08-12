Trading Essentials: Quickstart | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/ems-api/how-to-guides/trading-essentials-quickstart)

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

On this page

Trading Essentials: Quickstart
==============================

Introduction[​](/ems-api/how-to-guides/trading-essentials-quickstart#introduction "Direct link to Introduction")
----------------------------------------------------------------------------------------------------------------

In this tutorial, you'll learn how to leverage our crypto trading API to automate and streamline your trading across multiple exchanges.
Discover how to connect your accounts, execute trades, and efficiently manage your portfolio with just a few clicks.

With our solution, you gain the power to control trades on various exchanges using just one API.

Background[​](/ems-api/how-to-guides/trading-essentials-quickstart#background "Direct link to Background")
----------------------------------------------------------------------------------------------------------

The EMS Trading API lets you manage multiple trading accounts on different exchanges all in one place, making trading easier with combined and consistent data.

It gives you up-to-date market info, past data, and options to use it through the cloud or on your systems.

Perfect for traders, big companies, and experts like developers and analysts, this API is fast, efficient, and reliable, providing a complete trading solution with easy access to unique insights and information.

On the Agenda[​](/ems-api/how-to-guides/trading-essentials-quickstart#on-the-agenda "Direct link to On the Agenda")
-------------------------------------------------------------------------------------------------------------------

* **Obtain a Free API Key**: Secure your gateway to multi-exchange trading with a free API key from our site.
* **Check available exchanges**: Verify the list of supported exchanges via `EMS API`
* **Connect your Exchanges**: Quickly integrate your accounts with exchanges like `BITMEX` and `KRAKEN`.
* **Execute BUY on KRAKEN**: Check your balance, initiate the `BUY` order, and confirm the status of the order
* **Execute SELL on KRAKEN**: Initiate `SELL` order and check the order status report

Getting started[​](/ems-api/how-to-guides/trading-essentials-quickstart#getting-started "Direct link to Getting started")
-------------------------------------------------------------------------------------------------------------------------

To execute the EMS Trading API, you'll need a [Free API Key](https://www.coinapi.io/get-free-api-key?product_id=ems-api) from our website.

Check available exchanges[​](/ems-api/how-to-guides/trading-essentials-quickstart#check-available-exchanges "Direct link to Check available exchanges")
-------------------------------------------------------------------------------------------------------------------------------------------------------

To access a list of supported exchanges that can be connected via the EMS API, execute the following:

```
import requests  
  
url = "https://ems-mgmt.coinapi.io/v1/exchanges"  
  
payload={}  
headers = {  
  'Accept': 'application/json',  
  'X-CoinAPI-Key': '73034021-THIS-IS-SAMPLE-COINAPI-KEY'  
}  
  
response = requests.request("GET", url, headers=headers, data=payload)  
  
print(response.text)
```

Here's a snippet extracted from the server's reply:

```
[  
	{  
		"exchange_id": "BITMEX",  
		"location_id": "aws-eu-west-1-prd",  
		"required_parameters": [  
			"PrivateApiKey",  
			"PublicApiKey"  
		]  
	},  
	{  
		"exchange_id": "COINBASE",  
		"location_id": "aws-us-east-1-prd",  
		"required_parameters": [  
			"PassPhrase",  
			"PrivateApiKey",  
			"PublicApiKey"  
		]  
	},  
    	{  
		"exchange_id": "GEMINI",  
		"location_id": "aws-us-east-1-prd",  
		"required_parameters": [  
			"PrivateApiKey",  
			"PublicApiKey"  
		]  
	},  
	{  
		"exchange_id": "KRAKEN",  
		"location_id": "aws-us-west-2-prd",  
		"required_parameters": [  
			"PrivateApiKey",  
			"PublicApiKey"  
		]  
	}  
]  
// other exchanges and their parameters...
```

info

To access the full list of supported exchanges, you can execute the endpoint <https://ems-mgmt.coinapi.io/v1/exchanges>. Above, we only showcase a partial list as an example.

Connect your Exchanges[​](/ems-api/how-to-guides/trading-essentials-quickstart#connect-your-exchanges "Direct link to Connect your Exchanges")
----------------------------------------------------------------------------------------------------------------------------------------------

To begin trading on cryptocurrency exchanges, you'll need to connect your accounts.
Below are examples of integrating with two popular exchanges:

* [BITMEX example](/ems-api/how-to-guides/trading-essentials-quickstart#bitmex)
* [KRAKEN example](/ems-api/how-to-guides/trading-essentials-quickstart#kraken)

info

While the examples in this quickstart provided are focused on integrating with `BITMEX` and `KRAKEN`, the process is quite similar for various exchanges.

### BITMEX[​](/ems-api/how-to-guides/trading-essentials-quickstart#bitmex "Direct link to BITMEX")

BITMEX stands as a premier cryptocurrency exchange, offering a robust platform for traders and investors worldwide.

### Obtain Public key[​](/ems-api/how-to-guides/trading-essentials-quickstart#obtain-public-key "Direct link to Obtain Public key")

To begin trading on BITMEX, you'll need to obtain your public and private keys from [BITMEX](https://www.bitmex.com/).

### Connect your account[​](/ems-api/how-to-guides/trading-essentials-quickstart#connect-your-account "Direct link to Connect your account")

After acquiring keys, the initial step includes sharing your exchange keys
through the account creation process for the designated exchange.

```
import requests  
import json  
  
url = "https://ems-mgmt.coinapi.io/v1/accounts"  
  
payload = {  
    "exchange_id": "BITMEX/JOHN",  
    "parameters": [  
        {  
            "key": "PublicApiKey",  
            "value": "73034021-THIS-IS-SAMPLE-PUBLIC-KEY-FROM-BITMEX"  
        },  
                {  
            "key": "PrivateApiKey",  
            "value": "73034021-THIS-IS-SAMPLE-PRIVATE-KEY-FROM-BITMEX"  
        }  
    ]  
}  
  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Convert payload to JSON string  
json_payload = json.dumps(payload)  
  
# Make the request  
response = requests.post(url, data=json_payload, headers=headers)  
  
# Print the response  
print("Response Code:", response.status_code)
```

Once the update is successful, you'll receive an HTTP status code of `200`.

### KRAKEN[​](/ems-api/how-to-guides/trading-essentials-quickstart#kraken "Direct link to KRAKEN")

### Obtain Public key[​](/ems-api/how-to-guides/trading-essentials-quickstart#obtain-public-key-1 "Direct link to Obtain Public key")

To begin trading on KRAKEN, you'll need to obtain your public and private keys from [KRAKEN](https://www.kraken.com).

### Connect your account[​](/ems-api/how-to-guides/trading-essentials-quickstart#connect-your-account-1 "Direct link to Connect your account")

After acquiring keys, the initial step includes sharing your exchange keys
through the account creation process for the designated exchange.

```
import requests  
import json  
  
url = "https://ems-mgmt.coinapi.io/v1/accounts"  
  
payload = {  
    "exchange_id": "KRAKEN/JOHN",  
    "parameters": [  
        {  
            "key": "PublicApiKey",  
            "value": "73034021-THIS-IS-SAMPLE-PUBLIC-KEY-FROM-KRAKEN"  
        },  
                {  
            "key": "PrivateApiKey",  
            "value": "73034021-THIS-IS-SAMPLE-PRIVATE-KEY-FROM-KRAKEN"  
        }  
    ]  
}  
  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Convert payload to JSON string  
json_payload = json.dumps(payload)  
  
# Make the request  
response = requests.post(url, data=json_payload, headers=headers)  
  
# Print the response  
print("Response Code:", response.status_code)
```

Get the list of Connected Exchanges[​](/ems-api/how-to-guides/trading-essentials-quickstart#get-the-list-of-connected-exchanges "Direct link to Get the list of Connected Exchanges")
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

To check which accounts have been created on our side, execute the following code:

```
import requests  
import json  
  
url = "https://ems-mgmt.coinapi.io/v1/accounts"  
  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY"  
}  
  
# Make the request  
response = requests.get(url, headers=headers)  
  
if response.status_code == 200:  
    accounts_json = response.json()  
    print(json.dumps(accounts_json, indent=4))  
else:  
    print("Error:", response.status_code)
```

Here's an example response, listing all accounts created with your API KEY:

```
[  
    {  
        "exchange_id": "BITMEX/JOHN",  
        "parameters": [  
            {  
                "key": "PublicApiKey",  
                "value": "73034021-THIS-IS-SAMPLE-PUBLIC-KEY-FROM-BITMEX"  
            },  
            {  
                "key": "PrivateApiKey",  
                "value": "73034021-THIS-IS-SAMPLE-PRIVATE-KEY-FROM-BITMEX"  
            }  
        ]  
    },  
    {  
        "exchange_id": "KRAKEN/JOHN",  
        "parameters": [  
            {  
                "key": "PublicApiKey",  
                "value": "73034021-THIS-IS-SAMPLE-PUBLIC-KEY-FROM-KRAKEN"          
            },  
            {  
                "key": "PrivateApiKey",  
                "value": "73034021-THIS-IS-SAMPLE-PRIVATE-KEY-FROM-KRAKEN"  
            }  
        ]  
    }  
]
```

Trades execution[​](/ems-api/how-to-guides/trading-essentials-quickstart#trades-execution "Direct link to Trades execution")
----------------------------------------------------------------------------------------------------------------------------

Placing an order on an exchange involves providing instructions for executing a trade at a designated price and quantity.

### Check balance (Optional)[​](/ems-api/how-to-guides/trading-essentials-quickstart#check-balance-optional "Direct link to Check balance (Optional)")

Before diving into trading, it's a good idea to check the balance on your account(s).
Here's an example of checking the account balance for all of the exchanges associated with the account.

```
import requests  
import json  
  
url = "https://global.ems.coinapi.net/v1/balances"  
  
payload={}  
headers = {  
  'Accept': 'application/json',  
  'X-CoinAPI-Key': '73034021-THIS-IS-SAMPLE-COINAPI-KEY'  
}  
  
# Make the request  
response = requests.get(url, headers=headers)  
  
if response.status_code == 200:  
    accounts_json = response.json()  
    print(json.dumps(accounts_json, indent=4))  
else:  
    print("Error:", response.status_code)
```

The response may be as follows (for `BITMEX/JOHN` and `KRAKEN/JOHN` accounts):

```
[  
    {  
        "type": "BALANCE_SNAPSHOT",  
        "exchange_id": "BITMEX/JOHN",  
        "data": [  
            {  
                "id": "XBT",  
                "asset_id_exchange": "XBT",  
                "asset_id_coinapi": "BTC",  
                "balance": 0.02164794,  
                "available": 0.02164794,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",         
                "rate_usd": 52357.18111158658          
            },  
            {  
                "id": "BMEx",  
                "asset_id_exchange": "BMEx",  
                "asset_id_coinapi": "BMEX",  
                "balance": 300000.0,  
                "available": 300000.0,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",         
                "rate_usd": 0.2521371329127946         
            }  
        ]  
    },  
    {  
        "type": "BALANCE_SNAPSHOT",  
        "exchange_id": "KRAKEN/JOHN",  
        "data": [  
            {  
                "id": "ETHW",  
                "asset_id_exchange": "ETHW",  
                "asset_id_coinapi": "ETHW",  
                "balance": 1.73e-05,  
                "available": 1.73e-05,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": 2.9136466899640077  
            },  
            {  
                "id": "BCH",  
                "asset_id_exchange": "BCH",  
                "asset_id_coinapi": "BCH",  
                "balance": 2.9e-09,  
                "available": 2.9e-09,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": 265.7082181877394  
            },  
            {  
                "id": "ZCAD",  
                "asset_id_exchange": "ZCAD",  
                "asset_id_coinapi": "CAD",  
                "balance": 0.7905,  
                "available": 0.7905,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": 0.7405719177575096  
            },  
            {  
                "id": "ZEUR",  
                "asset_id_exchange": "ZEUR",  
                "asset_id_coinapi": "EUR",  
                "balance": 0.0098,  
                "available": 0.0098,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": 1.0809450373867444  
            },  
            {  
                "id": "ADA",  
                "asset_id_exchange": "ADA",  
                "asset_id_coinapi": "ADA",  
                "balance": 2e-08,  
                "available": 2e-08,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": 0.6244338769954291  
            },  
            {  
                "id": "ZUSD",  
                "asset_id_exchange": "ZUSD",  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": null  
            },  
            {  
                "id": "XXBT",  
                "asset_id_exchange": "XXBT",  
                "asset_id_coinapi": "BTC",  
                "balance": 8.58e-08,  
                "available": 8.58e-08,  
                "locked": 0.0,  
                "traded": 0.0,  
                "last_updated_by": "EXCHANGE",  
                "rate_usd": 52320.9229657045  
            }  
        ]  
    }  
]
```

### Submit Order (SELL)[​](/ems-api/how-to-guides/trading-essentials-quickstart#submit-order-sell "Direct link to Submit Order (SELL)")

Here's an example of submitting a `SELL` order on the `KRAKEN` exchange with the following details:

* Desired amount of USD to sell: `10`
* Expected price to be executed at: `150`
* Initial balance of USD: `77.3669`
* Save down somewhere the `YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001` identifier to track the status of the order

```
import requests  
import json  
from datetime import datetime, timedelta  
  
url = "https://global.ems.coinapi.net/v1/orders"  
  
payload = json.dumps({  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "symbol_id_coinapi": "KRAKEN_SPOT_USD_JPY",  
  "amount_order": 10,  
  "price": 150,  
  "side": "SELL",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "exec_inst": [  
    "MAKER_OR_CANCEL"  
  ]  
})  
  
# Headers  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Make the request  
try:  
    response = requests.post(url, data=payload, headers=headers)  
  
    # Check status code  
    if response.status_code == 200:  
        print("Response JSON:", response.json())  
    else:  
        print("Response Code:", response.status_code)  
    
except Exception as e:  
    print("An error occurred:", e)
```

Examples of Possible Responses:

* Successful Routing
* Invalid Volume Error
* Insufficient Funds Error

The order has been sent to the exchange:

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "client_order_id_format_exchange": "74733759",  
  "exchange_order_id": "OX6EKO-67KDQ-KGNYFI",  
  "amount_open": 10.0,  
  "amount_filled": 0.0,  
  "status": "ROUTED",  
  "status_history": [  
    ["RECEIVED", "2024-02-22T23:55:31.5424443Z"],  
    ["ROUTING", "2024-02-22T23:55:31.5439512Z"],  
    ["ROUTED", "2024-02-22T23:55:31.8127436Z"]  
  ],  
  "error_message": null,  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "symbol_id_exchange": "USDJPY",  
  "symbol_id_coinapi": "KRAKEN_SPOT_USD_JPY",  
  "amount_order": 10.0,  
  "price": 150.0,  
  "avg_px": 0.0,  
  "side": "SELL",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

If you encounter a volume error due to a mismatch with the minimum order size:

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "client_order_id_format_exchange": "74733759",  
  "exchange_order_id": null,  
  "amount_open": 5e-15,  
  "amount_filled": 0.0,  
  "status": "REJECTED",  
  "status_history": [  
    ["RECEIVED", "2024-02-23T00:04:36.8301287Z"],  
    ["ROUTING", "2024-02-23T00:04:36.8315182Z"],  
    ["REJECTED", "2024-02-23T00:04:36.9940661Z"]  
  ],  
  "error_message": "EGeneral:Invalid arguments:volume",  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "symbol_id_exchange": "USDJPY",  
  "symbol_id_coinapi": "KRAKEN_SPOT_USD_JPY",  
  "amount_order": 5e-15,  
  "price": 150.0,  
  "avg_px": 0.0,  
  "side": "SELL",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

If you encounter an insufficient funds error due to insufficient balance in your account:

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "client_order_id_format_exchange": "74733759",  
  "exchange_order_id": null,  
  "amount_open": 555555555555555.0,  
  "amount_filled": 0.0,  
  "status": "REJECTED",  
  "status_history": [  
    ["RECEIVED", "2024-02-23T00:05:34.6909879Z"],  
    ["ROUTING", "2024-02-23T00:05:34.6918765Z"],  
    ["REJECTED", "2024-02-23T00:05:34.8518753Z"]  
  ],  
  "error_message": "EGeneral:Invalid arguments:volume",  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "symbol_id_exchange": "USDJPY",  
  "symbol_id_coinapi": "KRAKEN_SPOT_USD_JPY",  
  "amount_order": 555555555555555.0,  
  "price": 150.0,  
  "avg_px": 0.0,  
  "side": "SELL",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

info

* [Here](https://docs.coinapi.io/ems-api/#oeml-order-params-exec) you can check the comprehensive list of execution instructions for the `exec_inst` parameter
* You can find available values for the `time_in_force` parameter [here](https://docs.coinapi.io/ems-api/#ems-order-params-tif)
* EMS exclusively supports the LIMIT [`order_type`](https://docs.coinapi.io/ems-api/#oeml-order-params-type).
* The supported values for `symbol_id_coinapi` can be found by executing the endpoint provided [here](https://docs.coinapi.io/market-data/rest-api/metadata/list-all-symbols).
* The meaning of the order `status` in the response (`ROUTED`, `REJECTED`, etc.) can be found [here](https://docs.coinapi.io/ems-api/#order-status-description)
* To view the possible values for the order lifecycle, [click here](https://docs.coinapi.io/ems-api/#order-status-lifecycle)
* Instead of utilizing CoinAPI's `symbol_id_coinapi`, you can opt for the symbol provided by the exchange through `symbol_id_exchange`

Here are some of the most common codes that may be returned for order creation:

| Http Status Code | Description |
| --- | --- |
| 200 (ok) | Order accepted |
| 400 (bad request) | Incorrect input parameters. |
| 490 (unreachable) | Exchange cannot be reached. |
| 504 (timeout) | Exchange didn't respond in the defined timeout. |

---

### Verify order status[​](/ems-api/how-to-guides/trading-essentials-quickstart#verify-order-status "Direct link to Verify order status")

Ensure that you've saved the `client_order_id` parameter associated with your specific order.
This identifier will be necessary to check its status.

```
import requests  
import json  
from datetime import datetime, timedelta  
  
url = "https://global.ems.coinapi.net/v1/orders/status/YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001"  
  
# Headers  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Make the request  
try:  
    response = requests.get(url, headers=headers)  
  
    # Check status code  
    if response.status_code == 200:  
        print("Response JSON:", response.json())  
    else:  
        print("Response Code:", response.status_code)  
          
    for header, value in response.headers.items():  
        print(header + ': ' + value)  
    
except Exception as e:  
    print("An error occurred:", e)
```

An example `order status report` that was executed with
`YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001` identifier and which was `CANCELED`.

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "client_order_id_format_exchange": "1945919824",  
  "exchange_order_id": "OUQMAY-ODBWL-AXG4ZE",  
  "amount_open": 10.0,  
  "amount_filled": 0.0,  
  "status": "CANCELED",  
  "status_history": [  
    ["RECEIVED", "2024-02-23T00:16:20.2139293Z"],  
    ["ROUTING", "2024-02-23T00:16:20.2389572Z"],  
    ["ROUTED", "2024-02-23T00:16:20.4016779Z"],  
    ["NEW", "2024-02-23T00:16:20.4021975Z"],  
    ["CANCELED", "2024-02-23T00:16:20.4026337Z"]  
  ],  
  "error_message": null,  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-001",  
  "symbol_id_exchange": "USDJPY",  
  "symbol_id_coinapi": "KRAKEN_SPOT_USD_JPY",  
  "amount_order": 10.0,  
  "price": 150.0,  
  "avg_px": 0.0,  
  "side": "SELL",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

### Check all open orders[​](/ems-api/how-to-guides/trading-essentials-quickstart#check-all-open-orders "Direct link to Check all open orders")

You can also check all of the `open` orders.

```
import requests  
import json  
from datetime import datetime, timedelta  
  
url = " https://global.ems.coinapi.net/v1/orders"  
  
# Headers  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Make the request  
try:  
    response = requests.get(url, headers=headers)  
  
    # Check status code  
    if response.status_code == 200:  
        print("Response JSON:", response.json())  
    else:  
        print("Response Code:", response.status_code)  
          
    for header, value in response.headers.items():  
        print(header + ': ' + value)  
    
except Exception as e:  
    print("An error occurred:", e)
```

info

After an order is closed/finalized, it will no longer be visible through the endpoint mentioned above.

### Submit Order (BUY)[​](/ems-api/how-to-guides/trading-essentials-quickstart#submit-order-buy "Direct link to Submit Order (BUY)")

Here's an example of submitting a `BUY` order on the `KRAKEN` exchange with the following details:

* Desired amount of `OXT` to buy: `100`
* Expected price to be executed at: `0.11`
* Save down somewhere the `YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007` identifier to track the status of the order

```
import requests  
import json  
from datetime import datetime, timedelta  
  
url = "https://global.ems.coinapi.net/v1/orders"  
  
payload = json.dumps({  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "symbol_id_coinapi": "KRAKEN_SPOT_OXT_USD",  
  "amount_order": 100,  
  "price": 0.11,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "exec_inst": [  
    "MAKER_OR_CANCEL"  
  ]  
})  
  
# Headers  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Make the request  
try:  
    response = requests.post(url, data=payload, headers=headers)  
  
    # Check status code  
    if response.status_code == 200:  
        print("Response JSON:", response.json())  
    else:  
        print("Response Code:", response.status_code)  
          
    for header, value in response.headers.items():  
        print(header + ': ' + value)  
    
except Exception as e:  
    print("An error occurred:", e)
```

Successfully routed order Response:

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "client_order_id_format_exchange": "1946142760",  
  "exchange_order_id": "OJCPEO-PO7WD-VTPUF2",  
  "amount_open": 100.0,  
  "amount_filled": 0.0,  
  "status": "ROUTED",  
  "status_history": [  
    ["RECEIVED", "2024-02-23T01:13:15.6096269Z"],  
    ["ROUTING", "2024-02-23T01:13:15.6102840Z"],  
    ["ROUTED", "2024-02-23T01:13:15.7772494Z"]  
  ],  
  "error_message": null,  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "symbol_id_exchange": "OXTUSD",  
  "symbol_id_coinapi": "KRAKEN_SPOT_OXT_USD",  
  "amount_order": 100.0,  
  "price": 0.11,  
  "avg_px": 0.0,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

Below is the `order status report` response for a `BUY` operation with the `client_order_id` set as `YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007`:

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "client_order_id_format_exchange": "1946142760",  
  "exchange_order_id": "OJCPEO-PO7WD-VTPUF2",  
  "amount_open": 100.0,  
  "amount_filled": 0.0,  
  "status": "NEW",  
  "status_history": [  
    ["RECEIVED", "2024-02-23T01:13:15.6096269Z"],  
    ["ROUTING", "2024-02-23T01:13:15.6102840Z"],  
    ["ROUTED", "2024-02-23T01:13:15.7772494Z"],  
    ["NEW", "2024-02-23T01:13:15.8077026Z"]  
  ],  
  "error_message": null,  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "symbol_id_exchange": "OXTUSD",  
  "symbol_id_coinapi": "KRAKEN_SPOT_OXT_USD",  
  "amount_order": 100.0,  
  "price": 0.11,  
  "avg_px": 0.0,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

### Cancelling all open orders[​](/ems-api/how-to-guides/trading-essentials-quickstart#cancelling-all-open-orders "Direct link to Cancelling all open orders")

To cancel all open orders associated with the `KRAKEN/JOHN`:

```
import requests  
import json  
from datetime import datetime, timedelta  
  
url = "https://global.ems.coinapi.net/v1/orders/cancel/all"  
  
payload = json.dumps({"exchange_id ": "KRAKEN/JOHN"})  
  
# Headers  
headers = {  
    "X-CoinAPI-Key": "73034021-THIS-IS-SAMPLE-COINAPI-KEY",  
    "Content-Type": "application/json"  
}  
  
# Make the request  
try:  
    response = requests.post(url, data=payload, headers=headers)  
  
    # Check status code  
    if response.status_code == 200:  
        print("Response JSON:", response.json())  
    else:  
        print("Response Code:", response.status_code)  
          
    for header, value in response.headers.items():  
        print(header + ': ' + value)  
    
except Exception as e:  
    print("An error occurred:", e)
```

Here's a sample order report for a canceled `BUY` order via the `EMS API`:

```
{  
  "type": "ORDER_EXEC_REPORT_UPDATE",  
  "id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "client_order_id_format_exchange": "1946142760",  
  "exchange_order_id": "OJCPEO-PO7WD-VTPUF2",  
  "amount_open": 100.0,  
  "amount_filled": 0.0,  
  "status": "CANCELED",  
  "status_history": [  
    ["RECEIVED", "2024-02-23T01:13:15.6096269Z"],  
    ["ROUTING", "2024-02-23T01:13:15.6102840Z"],  
    ["ROUTED", "2024-02-23T01:13:15.7772494Z"],  
    ["NEW", "2024-02-23T01:13:15.8077026Z"],  
    ["PENDING_CANCEL", "2024-02-23T01:18:49.2279836Z"],  
    ["CANCELED", "2024-02-23T01:18:49.4245926Z"]  
  ],  
  "error_message": null,  
  "fills": [],  
  "exchange_id": "KRAKEN/JOHN",  
  "client_order_id": "YOUR-UNIQUE-IDENTIFIER-FOR-ORDER-007",  
  "symbol_id_exchange": "OXTUSD",  
  "symbol_id_coinapi": "KRAKEN_SPOT_OXT_USD",  
  "amount_order": 100.0,  
  "price": 0.11,  
  "avg_px": 0.0,  
  "side": "BUY",  
  "order_type": "LIMIT",  
  "time_in_force": "GOOD_TILL_CANCEL",  
  "expire_time": null,  
  "exec_inst": ["MAKER_OR_CANCEL"]  
}
```

The explanations and practical code examples provided should let you have a better understanding
of how to leverage the `EMS API` for cryptocurrency trading across multiple exchanges.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

* [Introduction](/ems-api/how-to-guides/trading-essentials-quickstart#introduction)
* [Background](/ems-api/how-to-guides/trading-essentials-quickstart#background)
* [On the Agenda](/ems-api/how-to-guides/trading-essentials-quickstart#on-the-agenda)
* [Getting started](/ems-api/how-to-guides/trading-essentials-quickstart#getting-started)
* [Check available exchanges](/ems-api/how-to-guides/trading-essentials-quickstart#check-available-exchanges)
* [Connect your Exchanges](/ems-api/how-to-guides/trading-essentials-quickstart#connect-your-exchanges)
  + [BITMEX](/ems-api/how-to-guides/trading-essentials-quickstart#bitmex)
  + [Obtain Public key](/ems-api/how-to-guides/trading-essentials-quickstart#obtain-public-key)
  + [Connect your account](/ems-api/how-to-guides/trading-essentials-quickstart#connect-your-account)
  + [KRAKEN](/ems-api/how-to-guides/trading-essentials-quickstart#kraken)
  + [Obtain Public key](/ems-api/how-to-guides/trading-essentials-quickstart#obtain-public-key-1)
  + [Connect your account](/ems-api/how-to-guides/trading-essentials-quickstart#connect-your-account-1)
* [Get the list of Connected Exchanges](/ems-api/how-to-guides/trading-essentials-quickstart#get-the-list-of-connected-exchanges)
* [Trades execution](/ems-api/how-to-guides/trading-essentials-quickstart#trades-execution)
  + [Check balance (Optional)](/ems-api/how-to-guides/trading-essentials-quickstart#check-balance-optional)
  + [Submit Order (SELL)](/ems-api/how-to-guides/trading-essentials-quickstart#submit-order-sell)
  + [Verify order status](/ems-api/how-to-guides/trading-essentials-quickstart#verify-order-status)
  + [Check all open orders](/ems-api/how-to-guides/trading-essentials-quickstart#check-all-open-orders)
  + [Submit Order (BUY)](/ems-api/how-to-guides/trading-essentials-quickstart#submit-order-buy)
  + [Cancelling all open orders](/ems-api/how-to-guides/trading-essentials-quickstart#cancelling-all-open-orders)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.