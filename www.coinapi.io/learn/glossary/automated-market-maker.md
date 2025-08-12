CoinAPI.io Glossary - Automated Market Maker (AMM)

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

### Automated Market Maker (AMM)

Automated Market Maker (AMM) is a decentralized trading protocol that enables automatic trading between cryptocurrency pairs using liquidity pools instead of traditional order books.

Table of Contents

* [What is Automated Market Maker (AMM)?](#link-3ea3d51f3a77)
* [How Automated Market Makers Work](#link-a0785fc152c9)
* [Types of AMM Models](#link-d6ecc4385ee7)
* [Popular Examples of AMMs](#link-8f4c28570542)
* [Risks Associated with First-Generation AMMs](#link-e5637ef04880)
* [Improvements and Future Developments in AMM Models](#link-64aeec7a8835)
* [Things to Remember](#link-1f6334cd0aa7)

What is Automated Market Maker (AMM)?
-------------------------------------

An Automated Market Maker (AMM) is a decentralized protocol used by [Decentralized Exchanges (DEXs)](https://www.coinapi.io/learn/glossary/decentralized-exchange-dex) to facilitate cryptocurrency trading without traditional order books or intermediaries. Instead of matching buyers and sellers, AMMs enable users to trade their digital assets directly against [liquidity pools](https://www.coinapi.io/learn/glossary/liquidity-pool). Liquidity providers fund these pools and use [smart contracts](https://www.coinapi.io/learn/glossary/smart-contract) to maintain [liquidity](https://www.coinapi.io/learn/glossary/liquidity). Trades are executed instantly based on predefined mathematical formulas that determine asset prices. This mechanism allows for continuous liquidity, reduced trading fees, and a more accessible trading environment within the [Decentralized Finance (DeFi)](https://www.coinapi.io/learn/glossary/defi-decentralized-finance) ecosystem.

How Automated Market Makers Work
--------------------------------

AMMs replace traditional order books with liquidity pools governed by smart contracts. Liquidity providers deposit pairs of [tokens](https://www.coinapi.io/learn/glossary/token) into these pools. They maintain a balance that follows a specific mathematical formula, such as the constant product formula (x \* y = k). When a user initiates a trade, the AMM adjusts the token ratios in the pool according to the formula. This ensures that the overall value remains constant. Prices are determined automatically based on supply and demand within the pool. There is no need for a counterparty, enabling seamless and permissionless trading.

Types of AMM Models
-------------------

AMM models use different mathematical formulas to manage liquidity pools and determine prices:

1. **Constant Product Market Maker (CPMM):** Uses the formula x \* y = k, where x and y are the quantities of two tokens, and k is a constant. Popularized by Uniswap, this model ensures that the product of the token reserves remains unchanged after each trade.
2. **Constant Sum Market Maker (CSMM):** Employs the formula x + y = k, focusing on maintaining a constant sum of token reserves. This model minimizes slippage for small trades but can face liquidity issues during large trades.
3. **Constant Mean Market Maker (CMMM):** Extends CPMM by supporting multiple tokens within a pool and uses the geometric mean of reserves in its formula. A balancer is a notable example that allows customizable token weights beyond the typical 50:50 ratio.

Popular Examples of AMMs
------------------------

Several AMMs are prominent within the DeFi space due to their reliability and features:

* **Uniswap:** An Ethereum-based DEX utilizing the CPMM model, Uniswap has evolved through multiple versions. It has enhanced liquidity provision and introduced features like concentrated liquidity in V3.
* **Curve Finance:** Specializes in stablecoin trading with low slippage by leveraging a unique AMM model tailored for pegged assets. This makes it ideal for large trades involving stablecoins.
* **Balancer:** Implements the CMMM model, allowing multi-asset pools and customizable token weights. This provides greater flexibility and deeper liquidity compared to traditional two-token pools.

Risks Associated with First-Generation AMMs
-------------------------------------------

While AMMs offer many advantages, they also have inherent risks:

* **[Impermanent Loss](https://www.coinapi.io/learn/glossary/impermanent-loss):** Occurs when the price ratio of pooled assets changes. This can lead to losses for liquidity providers compared to simply holding the assets.
* **[Slippage](https://www.coinapi.io/learn/glossary/slippage) Risks:** Large trades can significantly impact the pool's token ratios. This causes the executed price to differ from the expected price at the time of order submission.
* **Smart Contract Vulnerabilities:** AMMs operate on smart contracts. Any bugs or security flaws can be exploited by malicious actors, leading to potential loss of funds.
* **Limited Asset Availability:** AMMs may only support a limited range of trading pairs. This restricts access to a broader market of assets available on traditional exchanges.

Improvements and Future Developments in AMM Models
--------------------------------------------------

To address the limitations of first-generation AMMs, ongoing developments focus on enhancing efficiency, security, and user experience:

* **Hybrid AMM Models:** Combine elements from different AMM types to balance liquidity provision and price stability. This aims to reduce slippage and impermanent loss.
* **Integration of External Price Oracles:** Utilize off-chain data sources to improve price accuracy. This reduces reliance solely on internal pool dynamics and enhances capital efficiency.
* **Synthetic Assets:** Introduce virtualized tokens that represent underlying assets. This allows for more secure trading and advanced financial products like futures and options without directly handling the base assets.

These advancements aim to create more robust, efficient, and user-friendly AMM systems, further integrating them into the expanding DeFi landscape.

Things to Remember
------------------

* **Decentralized Trading Mechanism:** AMMs enable cryptocurrency trading without traditional order books by utilizing liquidity pools and smart contracts. This ensures continuous liquidity and instant trade execution.
* **Diverse AMM Models:** Different AMM models like CPMM, CSMM, and CMMM use unique mathematical formulas to manage liquidity and determine asset prices. Each offers distinct advantages for various trading scenarios.
* **Leading AMM Platforms:** Platforms such as Uniswap, Curve Finance, and Balancer are prominent examples of AMMs. Each offers specialized features like stablecoin optimization, multi-asset pools, and customizable token weights to cater to diverse user needs.
* **Associated Risks:** Despite their benefits, AMMs come with risks including impermanent loss, slippage, smart contract vulnerabilities, and limited asset availability. Liquidity providers and traders must carefully consider these factors.

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