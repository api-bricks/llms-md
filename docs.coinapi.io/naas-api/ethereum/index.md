Ethereum | CoinAPI.io Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![CoinAPI.io](/img/logo.svg)![CoinAPI.io](/img/logo.svg)](https://www.coinapi.io)

[Products](/naas-api/ethereum/)

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

* [NaaS API](/naas-api/)
* [Authentication](/naas-api/authentication)
* [API limits and billing](/naas-api/api-limits-and-billing-metrics)
* [Bitcoin](/naas-api/bitcoin/)
* [Ethereum](/naas-api/ethereum/)

  + [Methods](/naas-api/ethereum/Methods/eth_blockNumber)

* Ethereum

On this page

Ethereum
========

To access the ethereum blockchain documentation, please visit [ethereum.org](https://ethereum.org/en/developers/docs/).

Clients[​](/naas-api/ethereum/#clients "Direct link to Clients")
----------------------------------------------------------------

Clients are software implementations that enable nodes to participate in the network.

In our infrastructure, we currently support two major Ethereum clients: `Geth` and `Erigon`.
Users can interact with these clients through dedicated [endpoints](/naas-api/ethereum/#endpoints).

* Our support extends to both the `archived` and `current` versions of `Geth`.
  The archived variant encapsulates historical data, while the current version mirrors the latest state of the Ethereum network.
* For users leveraging `Erigon`, we provide access to `archived` versions

The `archived` mode clients are tailored for historical analysis and research,
while the `current` mode clients deliver real-time data for applications requiring the latest Ethereum network state.

info

When interacting with the Ethereum network using the endpoint `mainnet-ethereum.node.coinapi.io`,
it's important to note that queries may be directed to either `geth` or `erigon` based on our infrastructure's load balancing.

Endpoints[​](/naas-api/ethereum/#endpoints "Direct link to Endpoints")
----------------------------------------------------------------------

The following lists all the Ethereum network endpoints supported by NaaS API.

| Chain | Network | Node URL | Protocol | Software | Software Version | Mode |
| --- | --- | --- | --- | --- | --- | --- |
| **Ethereum** | Mainnet | <https://ethereum-mainnet.node.coinapi.io> | https |  |  |  |
| **Ethereum** | Mainnet | wss://ethereum-mainnet.node.coinapi.io | ws |  |  |  |
|  |  |  |  |  |  |  |
| **Ethereum** | Mainnet | <https://ethereum-mainnet-erigon.node.coinapi.io> | https | erigon | v.2.48.1 | **archived** |
| **Ethereum** | Mainnet | wss://ethereum-mainnet-erigon.node.coinapi.io | ws | erigon | v.2.48.1 | **archived** |
|  |  |  |  |  |  |  |
| **Ethereum** | Mainnet | <https://ethereum-mainnet-geth-archive.node.coinapi.io> | https | erigon | v.2.48.1 | **archived** |
| **Ethereum** | Mainnet | wss://ethereum-mainnet-geth-archive.node.coinapi.io | ws | erigon | v.2.48.1 | **archived** |
|  |  |  |  |  |  |  |
| **Ethereum** | Mainnet | <https://ethereum-mainnet-geth-current.node.coinapi.io> | https | geth | v.1.12.0 | **current** |
| **Ethereum** | Mainnet | wss://ethereum-mainnet-geth-current.node.coinapi.io | wss | geth | v.1.12.0 | **current** |
|  |  |  |  |  |  |  |
| **Ethereum** | Mainnet | <https://ethereum-mainnet-quicknode.node.coinapi.io> | https | geth | v.1.12.0 | **archived** |
| **Ethereum** | Mainnet | wss://ethereum-mainnet-quicknode.node.coinapi.io | wss | geth | v.1.12.0 | **archived** |
|  |  |  |  |  |  |  |

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

listtransactions](/naas-api/bitcoin/Methods/listtransactions)[Next

eth\_blockNumber](/naas-api/ethereum/Methods/eth_blockNumber)

* [Clients](/naas-api/ethereum/#clients)
* [Endpoints](/naas-api/ethereum/#endpoints)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.