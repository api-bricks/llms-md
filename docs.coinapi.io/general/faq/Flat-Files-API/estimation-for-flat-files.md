How to get an estimation for Flat Files data | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/general/faq/Flat-Files-API/estimation-for-flat-files)

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

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [FAQ](/general/faq/)

  + [General](/general/faq/general/)
  + [API Usage and Limits](/general/faq/API-Usage-and-Limits/)
  + [Billing, Payment, and Subscriptions](/general/faq/Billing-Payment-and-Subscriptions/)
  + [Account Management](/general/faq/Account-Management/)
  + [Security and Privacy](/general/faq/Security-and-Privacy/)
  + [API Access & Integration](/general/faq/API-Access-and-Integration/)
  + [Market Data API](/general/faq/Market-Data-API/)
  + [EMS Trading API](/general/faq/EMS-Trading-API/)
  + [Indexes API](/general/faq/Indexes-API/)
  + [Flat Files API](/general/faq/Flat-Files-API/)

    - [How to get an estimation for Flat Files data](/general/faq/Flat-Files-API/estimation-for-flat-files)
  + [Exchange Rates API](/general/faq/Exchange-Rates-API/)
  + [Node as a Service](/general/faq/Node-as-a-Service/)
  + [Enterprise Plan](/general/faq/Enterprise-Plan/)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* [FAQ](/general/faq/)
* [Flat Files API](/general/faq/Flat-Files-API/)
* How to get an estimation for Flat Files data

On this page

How to get an estimation for Flat Files data
============================================

This is a guide on how to get the size, files, and amount of a specific dataset using the Flat Files product. You may use the script below to get an estimation of the data that you are planning to purchase using our Flat Files product.

Python Script[​](/general/faq/Flat-Files-API/estimation-for-flat-files#python-script "Direct link to Python Script")
--------------------------------------------------------------------------------------------------------------------

```
#!/usr/bin/env python3  
  
# =================================================================  
# CONFIGURATION VARIABLES - Modify these as needed  
# =================================================================  
  
# Your CoinAPI Flat Files API Key  
API_KEY = "Flat-Files-API-Key"  
  
# AWS Configuration  
AWS_SECRET_KEY = "coinapi"  
AWS_REGION = "us-east-1"  
  
# Default settings  
DEFAULT_EXCHANGE = "BINANCE" # Example using CoinAPI exchange_id  
DEFAULT_START_DATE = "2024-01-01"  
DEFAULT_END_DATE = "2024-12-31"  
DEFAULT_DATA_TYPES = ["TRADES"]  # Options: TRADES, QUOTES, LIMITBOOK_FULL  
  
# Set to None or [] to process all symbols/assets  
DEFAULT_SYMBOLS = ["BINANCE_SPOT_BTC_USDT"] # Example using full CoinAPI symbol format  
DEFAULT_ASSETS = None   # Example: ["BTC", "ETH"] for specific assets  
  
# S3 endpoint configuration  
ENDPOINT_URL = "https://s3.flatfiles.coinapi.io"  
  
# Output configuration  
DEFAULT_OUTPUT_FORMAT = "text"  # Options: text, json  
DEFAULT_OUTPUT_FILE = "output.txt"  # Set to None for console output, or specify path like "output.txt"  
  
# =================================================================  
# Script implementation - Do not modify below this line unless needed  
# =================================================================  
  
import re  
from datetime import datetime, timedelta  
import subprocess  
import os  
from typing import List, Dict, Tuple  
import json  
import sys  
import io  
from pathlib import Path  
  
class CoinAPIS3Calculator:  
    def __init__(self, api_key: str, endpoint_url: str):  
        self.endpoint_url = endpoint_url  
        self.api_key = api_key  
          
    def parse_s3_line(self, line: str) -> Tuple[str, int]:  
        """Parse a single line from s3 ls output."""  
        parts = line.strip().split()  
        if len(parts) < 4:  
            return None, 0  
              
        size = int(parts[2])  
        filename = parts[3]  
          
        # Extract full symbol from SC (Symbol Class) identifier  
        symbol_match = re.search(r'SC-([A-Z]+_SPOT_[^+]+)', filename)  
        if not symbol_match:  
            print(f"Debug: Could not parse symbol from filename: {filename}", file=sys.stderr)  
            return "UNKNOWN", size  
              
        symbol = symbol_match.group(1)  
        return symbol, size  
          
    def get_s3_listing(self, exchange: str, date: str, data_type: str = "TRADES") -> str:  
        """Get S3 listing for specific exchange and date."""  
        path = f"s3://coinapi/T-{data_type}/D-{date}/E-{exchange}/"  
        print(f"Debug: Checking path: {path}", file=sys.stderr)  
        cmd = [  
            "aws",  
            "--endpoint-url", self.endpoint_url,  
            "--region", AWS_REGION,  
            "s3", "ls", path  
        ]  
          
        env = os.environ.copy()  
        env["AWS_ACCESS_KEY_ID"] = self.api_key  
        env["AWS_SECRET_ACCESS_KEY"] = AWS_SECRET_KEY  
          
        try:  
            result = subprocess.run(cmd, capture_output=True, text=True, check=True, env=env)  
            return result.stdout  
        except subprocess.CalledProcessError as e:  
            print(f"Error getting S3 listing: {e}", file=sys.stderr)  
            if e.stderr:  
                print(f"Error details: {e.stderr}", file=sys.stderr)  
            return ""  
  
    def filter_symbols(self, listing: str, symbols: List[str] = None, assets: List[str] = None) -> List[str]:  
        """Filter S3 listing by exact symbol class (SC) matches."""  
        if not symbols and not assets:  
            return listing.split('\n')  
              
        filtered_lines = []  
        for line in listing.split('\n'):  
            if not line.strip():  
                continue  
                  
            if symbols:  
                # Match exact CoinAPI symbol format with exact boundary  
                sc_patterns = [f"SC-{symbol}+" for symbol in symbols]  
                if not any(pattern in line for pattern in sc_patterns):  
                    continue  
                      
            if assets:  
                # For assets, check if any appear in the symbol part of filename  
                if not any(f"_{asset}_" in line.upper() for asset in [a.upper() for a in assets]):  
                    continue  
                      
            filtered_lines.append(line)  
              
        return filtered_lines  
  
    def calculate_day_size(self, exchange: str, date: str,   
                         data_type: str = "TRADES",  
                         symbols: List[str] = None,  
                         assets: List[str] = None) -> Dict:  
        """Calculate total size for a specific day with optional filtering."""  
        listing = self.get_s3_listing(exchange, date, data_type)  
        filtered_lines = self.filter_symbols(listing, symbols, assets)  
          
        total_size = 0  
        symbol_sizes = {}  
        file_count = 0  
        files_list = []  # Track actual filenames  
          
        for line in filtered_lines:  
            if not line.strip():  
                continue  
              
            parts = line.strip().split()  
            if len(parts) >= 4:  
                filename = parts[3]  
                date_str = date  
                files_list.append(f"{date_str}: {filename}")  
                  
            symbol, size = self.parse_s3_line(line)  
            if symbol:  
                total_size += size  
                symbol_sizes[symbol] = symbol_sizes.get(symbol, 0) + size  
                file_count += 1  
          
        return {  
            'total_size': total_size,  
            'symbols': symbol_sizes,  
            'file_count': file_count,  
            'files': files_list  
        }  
  
    def calculate_date_range(self,   
                           exchange: str,  
                           start_date: str,  
                           end_date: str,  
                           data_types: List[str] = ["TRADES"],  
                           symbols: List[str] = None,  
                           assets: List[str] = None) -> Dict:  
        """Calculate sizes for a date range with optional filtering."""  
        start = datetime.strptime(start_date, '%Y-%m-%d')  
        end = datetime.strptime(end_date, '%Y-%m-%d')  
          
        results = {  
            'total_size': 0,  
            'total_gb': 0,  
            'by_date': {},  
            'by_type': {dt: {'size': 0, 'files': 0, 'files_list': []} for dt in data_types},  
            'by_symbol': {}  
        }  
          
        current = start  
        while current <= end:  
            date_str = current.strftime('%Y%m%d')  
            results['by_date'][date_str] = {}  
              
            for data_type in data_types:  
                day_result = self.calculate_day_size(  
                    exchange, date_str, data_type, symbols, assets  
                )  
                  
                results['total_size'] += day_result['total_size']  
                results['by_type'][data_type]['size'] += day_result['total_size']  
                results['by_type'][data_type]['files'] += day_result['file_count']  
                results['by_type'][data_type]['files_list'].extend(day_result['files'])  
                  
                for symbol, size in day_result['symbols'].items():  
                    if symbol not in results['by_symbol']:  
                        results['by_symbol'][symbol] = 0  
                    results['by_symbol'][symbol] += size  
                  
                results['by_date'][date_str][data_type] = day_result  
              
            current += timedelta(days=1)  
            print(f"Processed {date_str}", file=sys.stderr)  
          
        results['total_gb'] = results['total_size'] / (1024**3)  
          
        for data_type in data_types:  
            results['by_type'][data_type]['size_gb'] = results['by_type'][data_type]['size'] / (1024**3)  
          
        results['by_symbol_gb'] = {  
            symbol: size / (1024**3)  
            for symbol, size in results['by_symbol'].items()  
        }  
          
        return results  
  
def print_size_report(results: Dict):  
    """Print a formatted report of the size calculations with detailed file listing."""  
    print("\nCoinAPI Flat Files Size Report")  
    print("=" * 80)  
      
    # Get symbol from the results  
    symbol = next(iter(results['by_symbol'].keys())) if results['by_symbol'] else "Unknown"  
      
    print(f"\nSymbol: {symbol}")  
    total_files = sum(info['files'] for info in results['by_type'].values())  
    print(f"Total Files: {total_files}")  
      
    # Print exact sizes per data type with file details  
    print("\nDetailed Size Breakdown:")  
    print("-" * 80)  
    for data_type, info in results['by_type'].items():  
        print(f"\n{data_type}:")  
        print(f"  Exact Size: {info['size']:,} bytes")  
        print(f"  Size in MB: {info['size'] / (1024**2):.2f} MB")  
        print(f"  Size in GB: {info['size'] / (1024**3):.6f} GB")  
        print(f"  Number of Files: {info['files']}")  
          
        # Print file details  
        if 'files_list' in info and info['files_list']:  
            print("\n  Files by date:")  
            for file_info in sorted(info['files_list']):  
                print(f"    - {file_info}")  
  
def main():  
    # Initialize calculator with configuration  
    calculator = CoinAPIS3Calculator(  
        api_key=API_KEY,  
        endpoint_url=ENDPOINT_URL  
    )  
      
    # Calculate results using default or configured values  
    results = calculator.calculate_date_range(  
        exchange=DEFAULT_EXCHANGE,  
        start_date=DEFAULT_START_DATE,  
        end_date=DEFAULT_END_DATE,  
        data_types=DEFAULT_DATA_TYPES,  
        symbols=DEFAULT_SYMBOLS,  
        assets=DEFAULT_ASSETS  
    )  
      
    # Prepare output content  
    output_content = ''  
    if DEFAULT_OUTPUT_FORMAT == 'json':  
        output_content = json.dumps(results, indent=2)  
    else:  
        string_buffer = io.StringIO()  
        sys.stdout = string_buffer  
        print_size_report(results)  
        sys.stdout = sys.__stdout__  
        output_content = string_buffer.getvalue()  
        string_buffer.close()  
      
    # Write to file or print to console  
    if DEFAULT_OUTPUT_FILE:  
        with open(DEFAULT_OUTPUT_FILE, 'w') as f:  
            f.write(output_content)  
        print(f"Results written to {DEFAULT_OUTPUT_FILE}", file=sys.stderr)  
    else:  
        print(output_content)  
  
if __name__ == "__main__":  
    main()
```

Variables[​](/general/faq/Flat-Files-API/estimation-for-flat-files#variables "Direct link to Variables")
--------------------------------------------------------------------------------------------------------

| Variables | Description |
| --- | --- |
| `API_KEY` | Your actual Flat Files API Key |
| `DEFAULT_EXCHANGE` | CoinAPI exchange\_id |
| `DEFAULT_START_DATE` | Start date of the requested data. Format: YYYY-MM-DD |
| `DEFAULT_END_DATE` | End date of the requested data. Format: YYYY-MM-DD |
| `DEFAULT_DATA_TYPES` | Options: TRADES, QUOTES, ORDERBOOKS |
| `DEFAULT_SYMBOLS` | CoinAPI Symbol e.g. BINANCE\_SPOT\_BTC\_USDT |
| `DEFAULT_ASSETS` | CoinAPI asset\_id. Example: ["BTC", "ETH"] for specific assets. (optional) |
| `DEFAULT_OUTPUT_FORMAT` | Options: text, json |
| `DEFAULT_OUTPUT_FILE` | Set to None for console output, or specify path like "output.txt" |

Response[​](/general/faq/Flat-Files-API/estimation-for-flat-files#response "Direct link to Response")
-----------------------------------------------------------------------------------------------------

Below is what the response would look like. (Note that the response below is only sample data, and not actual):

```
CoinAPI Flat Files Size Report  
  
Symbol: COINBASE_SPOT_BTC_USD  
Total Files: 100  
  
Detailed Size Breakdown:  
  
TRADES:  
  Exact Size: 1,073,741,824 bytes  
  Size in MB: 1073.741824 MB  
  Size in GB: 1 GB  
  Number of Files: 100  
  
  Files by date:  
    - 20240101: IDDI-12345+SC-COINBASE_SPOT_BTC_USD+S-BTC__002DUSD.csv.gz
```

Remember[​](/general/faq/Flat-Files-API/estimation-for-flat-files#remember "Direct link to Remember")
-----------------------------------------------------------------------------------------------------

Credits will also be consumed when listing the files based on our pricing model here: <https://docs.coinapi.io/flat-files-api/billing>

Sample Calculation[​](/general/faq/Flat-Files-API/estimation-for-flat-files#sample-calculation "Direct link to Sample Calculation")
-----------------------------------------------------------------------------------------------------------------------------------

Let's take the data from sample response as an example. Since the data is Trades and the pricing for Trades is $3.00 per GB. The total amount is $3 for 1 GB of Trades data.

Calculation:

Size in GB x Price per GB of the data type = Total Price of the data

Contact us[​](/general/faq/Flat-Files-API/estimation-for-flat-files#contact-us "Direct link to Contact us")
-----------------------------------------------------------------------------------------------------------

Our Sales Team is happy to discuss more about your business needs! If you have any questions, feel free to contact us here: <https://www.coinapi.io/contact-us>

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Flat Files API](/general/faq/Flat-Files-API/)[Next

Exchange Rates API](/general/faq/Exchange-Rates-API/)

* [Python Script](/general/faq/Flat-Files-API/estimation-for-flat-files#python-script)
* [Variables](/general/faq/Flat-Files-API/estimation-for-flat-files#variables)
* [Response](/general/faq/Flat-Files-API/estimation-for-flat-files#response)
* [Remember](/general/faq/Flat-Files-API/estimation-for-flat-files#remember)
* [Sample Calculation](/general/faq/Flat-Files-API/estimation-for-flat-files#sample-calculation)
* [Contact us](/general/faq/Flat-Files-API/estimation-for-flat-files#contact-us)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.