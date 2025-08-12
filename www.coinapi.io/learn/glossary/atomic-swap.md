CoinAPI.io Glossary - Atomic Swap

**🚀 Metrics API V2 Live:**

Complete Market Intelligence - CEX + DeFi Data in One API

[Learn More](https://www.coinapi.io/blog/metrics-api-v2-trading-volume-analysis-and-on-chain-metrics)

[![background](https://cdn.sanity.io/images/o65xz72l/production/268144c90959611dea3e360f81e4549c3cd03fd0-142x34.svg)![background](https://cdn.sanity.io/images/o65xz72l/production/e0ca0c29b08cb53631d77de4a84246da316d55d2-142x34.svg)](/)

* Products
* Use Cases
* Pricing
* Developers
* Resources
* Contact us
* [Log in](https://console.coinapi.io/)

### Atomic Swap

Atomic swaps enable peer-to-peer exchanges of crypto assets across separate blockchain networks. Through the use of a “virtual vault” known as a time-bound smart contract, funds can only be unlocked when both parties deposit the correct amount of assets.

Table of Contents

* [How Atomic Swaps Work](#link-d7e7072e63ce)
* [Advantages](#link-40517f30a771)
* [Disadvantages](#link-4a2704ca45d7)
* [Example Scenario](#link-92888e635bea)
* [Things to Remember](#link-298ac56c8cec)

Atomic Swap - Definition
========================

An **atomic swap** is a decentralized, peer-to-peer exchange of [**cryptocurrencies**](https://www.coinapi.io/learn/glossary/cryptocurrency) from separate [blockchain](https://www.coinapi.io/learn/glossary/blockchain) networks. It does not require a trusted third party or a centralized intermediary.

Using a specialized [smart contract](https://www.coinapi.io/learn/glossary/smart-contract) called a Hash Timelock Contract (HTLC), atomic swaps ensure that the [transaction](https://www.coinapi.io/learn/glossary/transaction-fees) either completes successfully with both parties receiving the agreed-upon assets or fails. If the swap fails, the funds are returned to their original owners.

How Atomic Swaps Work
---------------------

Atomic swaps use **HTLCs** as virtual vaults to lock funds and enforce swap conditions. Both parties deposit their respective cryptocurrencies into the HTLC, each locked with a **cryptographic hash** and a **timelock**.

The transaction proceeds only if both deposits are made correctly within the set time frame. If either party does not fulfill their part, the smart contract automatically refunds the assets to their original owners.

Advantages
----------

* **Decentralization:** Eliminates the need for [centralized exchanges](https://www.coinapi.io/learn/glossary/centralized-exchange-cex).
* **Security:** Reduces counterparty risks.
* **Lower Costs:** Minimizes transaction fees.
* **Increased [Liquidity](https://www.coinapi.io/learn/glossary/liquidity):** Enhances the tradability of assets across different blockchains.
* **Guaranteed Outcome:** Ensures that transactions are either completed fully or not at all.

Disadvantages
-------------

* **Complexity:** The technical nature of atomic swaps can be challenging for beginners.
* **Privacy Concerns:** Extended transaction times can make it easier for malicious actors to track and target users.
* **Limited Compatibility:** Atomic swaps are restricted to blockchains that support the same hashing algorithms.
* **User-Friendliness:** The process involves multiple steps and conditions.

Example Scenario
----------------

Consider a scenario where Alice wants to swap 10 X tokens with Bob for 10 Y tokens. They initiate an atomic swap by creating an **HTLC** that expires in one hour. Alice deposits her 10 X tokens into the contract, generating a private key and a cryptographic hash. Bob verifies the deposit and then deposits his 10 Y tokens into a new contract using the same hash. Alice can claim Bob's tokens by revealing the private key, which Bob then uses to withdraw Alice's tokens. If the swap is not completed within the hour, the funds are automatically returned to their original owners.

Things to Remember
------------------

* **Decentralized Exchange Mechanism:** Atomic swaps enable direct [peer-to-peer](https://www.coinapi.io/learn/glossary/peer-to-peer-trading) cryptocurrency exchanges across different blockchains without the need for centralized intermediaries.
* **Security Through Smart Contracts:** Utilizing **HTLCs**, atomic swaps ensure that transactions are either fully completed or entirely reverted, safeguarding participants' funds.
* **Interoperability and Liquidity:** By facilitating seamless cross-chain transactions, atomic swaps improve blockchain interoperability and unlock liquidity, crucial for the growth of the [**DeFi**](https://www.coinapi.io/learn/glossary/defi-decentralized-finance) ecosystem.
* **Technical Complexity and Compatibility:** While offering significant advantages, atomic swaps can be technically complex and are limited to blockchains with compatible hashing algorithms.

[![background](https://cdn.sanity.io/images/o65xz72l/production/99475f0760777c30125556b2707e1e8f77f2fba0-179x42.svg)](/)

###### Join our newsletter

* [![X](https://cdn.sanity.io/images/o65xz72l/production/89a93ecdd3eaa62f0d2bad091ff6d92a31e9c372-28x28.svg)](https://twitter.com/realcoinapi "X")
* [![Linkedin](https://cdn.sanity.io/images/o65xz72l/production/be666e8656abe83e43c1db9a3ab76d44b9af5cb5-28x28.svg)](https://www.linkedin.com/company/coinapi "Linkedin")
* [![Github](https://cdn.sanity.io/images/o65xz72l/production/80703d2d9baaef7e7f5471a54a720b9383a63aab-28x28.svg)](https://github.com/coinapi/coinapi-sdk "Github")
* [![T.me](https://cdn.sanity.io/images/o65xz72l/production/39be23a1db383ad12c3e9d4bebae9bc77bf59b8b-28x28.svg)](https://t.me/coinapiofficial "T.me")
* [![Discord](https://cdn.sanity.io/images/o65xz72l/production/9862f060f9b89536f18d4e8770a11bfb00c3e3fd-30x28.svg)](https://discord.gg/vgJbjjsVaC "Discord")
* [![Reddit](https://cdn.sanity.io/images/o65xz72l/production/d02e41d1eab87d289f2bc6a390bcd0c7def1b7ac-30x28.svg)](https://www.reddit.com/r/CoinAPI/ "Reddit")
* [![YouTube](https://cdn.sanity.io/images/o65xz72l/production/535425f0f99df8b6173d663721f8941430d637b2-28x28.svg)](https://www.youtube.com/@CoinAPI_Official "YouTube")
* [![G2](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F4b1d455c2cab4bf625e7cc96a1b74695c0b3c4bc-28x28.png&w=64&q=75)](https://www.g2.com/products/coinapi/reviews "G2")

###### Products

###### Products

* [Market Data API](/products/market-data-api)
* [Indexes API](/products/indexes-api)
* [EMS Trading API](/products/ems-api)
* [Flat Files](/products/flat-files)
* [Exchange Rates API](/products/exchange-rates-api)
* [Exchange Link](https://www.coinapi.io/products/exchange-link)

###### CoinAPI.io

###### CoinAPI.io

* [Home](https://www.coinapi.io/)
* [API Docs](https://docs.coinapi.io/?_gl=1*jgom05*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Blog](https://www.coinapi.io/blog)

###### Help

###### Help

* [Contact sales](/contact-us)
* [Contact support](https://console.coinapi.io/?link=/support-tickets)
* [How-to Guides](https://docs.coinapi.io/market-data/how-to-guides/?_gl=1*16m3ndl*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [FAQ](https://docs.coinapi.io/general/faq/?_gl=1*dfjpiw*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Metadata Explorer](https://docs.coinapi.io/market-data/metadata-tables/introduction)

###### Developers

###### Developers

* [Helper Libraries](https://github.com/api-bricks/api-bricks-sdk/)
* [API Documentation](https://docs.coinapi.io/?_gl=1*iuavdb*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)
* [Status Page](https://status.coinapi.io/?_gl=1*1ww1bbe*_gcl_au*NTIxNjU3NzExLjE3MzU1OTM0MTE.*_ga*OTI3MDg0NzQ2LjE3MzU1OTM0MDk.*_ga_063767QGZW*MTczODA3Mzc5MC43My4wLjE3MzgwNzM3OTAuNjAuMC4w*_ga_EXCQW96F7R*MTczODA3Mzc5MC4xMjEuMC4xNzM4MDczNzkwLjAuMC4w)

###### Legal

###### Legal

* [Terms of service](/legal#terms)
* [Acceptable Usage Policy](/legal#aup)
* [Privacy Policy](/legal#policy)

###### API Bricks brands

###### API Bricks brands

* [FinFeedAPI](https://finfeedapi.com/?utm_source=coinapi.io&utm_medium=referral&utm_campaign=footer)

![background](https://cdn.sanity.io/images/o65xz72l/production/5f005fa1cc9dc85c59ae054bb4a4838566b65c4e-25x26.svg)Copyright 2025 API BRICKS LTD F/K/A COINAPI LTD or its affiliates. All rights reserved.