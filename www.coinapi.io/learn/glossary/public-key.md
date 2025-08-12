CoinAPI.io Glossary - Public Key

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

### Public Key

Public key cryptography uses a pair of keys - a public one that can be freely shared and a private one kept secret. The public key can be used by anyone to encrypt messages or verify signatures, while only the holder of the matching private key can decrypt those messages or create valid signatures.

Table of Contents

* [How Public Key Encryption Works](#link-125931f3d117)
* [Advantages of Public Key Encryption](#link-f2561c4dacec)
* [Limitations of Public Key Encryption](#link-3c4ce8568c13)
* [Public Key in CoinAPI](#link-edbf8d33105c)
* [Things to Remember](#link-6caf237cf81f)

How Public Key Encryption Works
-------------------------------

In public key encryption, a user uses an algorithm to generate a cryptographic key pair. When someone wants to send a secure message, they encrypt the plaintext using the recipient's public key. The encrypted message, or ciphertext, can only be decrypted by the recipient's private key. This process ensures that even if the encrypted data is intercepted, it remains unreadable without the corresponding private key.

Advantages of Public Key Encryption
-----------------------------------

### Enhanced Security

Public key encryption eliminates the need for secure key distribution. The public key can be shared openly. Only the private key, known solely to the recipient, can decrypt the messages. This reduces the risk of unauthorized access.

### Digital Signatures

It supports digital signatures, ensuring the authenticity and integrity of messages. This feature verifies the sender's identity and prevents message tampering.

### Scalability

Public key encryption scales efficiently for large user bases. It is ideal for businesses, government agencies, and other organizations that require secure communication among many users.

### Non-Repudiation

It provides non-repudiation, meaning the sender cannot deny the authenticity of their sent messages. This is essential in legal and financial transactions where proof of origin is required.

### Integrity

Ensures that the message remains unchanged during transmission. Any alteration of the ciphertext can be detected, maintaining the integrity of the communication.

### Convenience

Public key encryption is user-friendly as it does not require the exchange of secret keys before communication. It is widely used in web applications and secure email systems for ease of implementation.

Limitations of Public Key Encryption
------------------------------------

### Potential for Security Breaches

If a private key is compromised, all messages encrypted with the corresponding public key can be decrypted. This poses a significant security risk.

### Susceptibility to Man-in-the-Middle Attacks

Attackers may intercept and impersonate communication parties to gain access to private keys. Implementing robust authentication and verification protocols is necessary to mitigate this risk.

### Performance Overheads

Public key encryption algorithms are generally slower and more resource-intensive compared to symmetric encryption methods. This makes them less suitable for applications requiring high-speed or large-scale data transfers.

Public Key in CoinAPI
---------------------

In the context of CoinAPI, public keys and private keys are integral components of the JWT (JSON Web Token) authentication process, which enhances the security of API interactions.

### Authentication Process with JWT

1. **Importing the Public Key:**  
- Access the CoinAPI's [customer portal](https://customerportal.coinapi.io/).  
- Navigate to the API Keys section.  
- Import your public JWT key (RSA or ECDSA) associated with your API key.

2. **Generating a JWT Token:**  
- Use your private key to generate a JWT token. This token includes claims that verify your identity and the permissions of your API key.  
- Ensure the token is signed correctly to maintain its integrity.

3. **Making Authenticated Requests:**  
- Include the generated JWT token in the `Authorization` the header of your API requests using the `Bearer JWT_TOKEN` format.

4. **Server Verification:**  
- Upon receiving your request, CoinAPI servers use the imported public key to verify the JWT token's signature.  
- If the token is valid and the signature matches, the server processes your request.

Things to Remember
------------------

* **Dual-Key System**: Public key encryption uses a pair of keys—a public key for encrypting data and a private key for decrypting it. This ensures that only the intended recipient can access the information.
* **Enhanced Security and Authentication**: It provides strong security by eliminating the need for secure key distribution. It supports digital signatures to verify the sender's identity and maintain message integrity.
* **Scalability and Convenience**: This encryption method efficiently scales for large organizations. It is user-friendly and does not require exchanging secret keys before communication.
* **Limitations and Risks**: While offering significant advantages, public key encryption can be vulnerable to security breaches if private keys are compromised. It may also suffer from performance overheads compared to symmetric encryption methods.

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