CoinAPI.io Blog - Anomaly Detection Crypto: Detecting Anomalies with CoinAPI’s Market Data API

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

March 15, 2023

Anomaly Detection Crypto: Detecting Anomalies with CoinAPI’s Market Data API
============================================================================

![featured image](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fa7e61b24803103316879d0f81f8e67ddd40f95e4-1000x500.png%3Frect%3D0%2C33%2C1000%2C435%26w%3D920%26h%3D400&w=1920&q=75)

***Detecting crypto anomalies is crucial for investors to make informed decisions. CoinAPI's [Market Data API](https://docs.coinapi.io/market-data/) provides a comprehensive solution to identify irregularities in the crypto market, empowering Axyon AI to deliver superior AI predictive solutions.***

Introduction to Anomaly Detection in Blockchain
-----------------------------------------------

Anomaly detection in blockchain refers to the process of identifying unusual patterns or behaviors within a blockchain system that may indicate potential security threats or irregularities. This process is crucial for maintaining the integrity and trustworthiness of blockchain networks.

By detecting anomalies, stakeholders can address issues before they escalate, ensuring the system remains secure and reliable. Techniques for anomaly detection in blockchain include machine learning algorithms, statistical analysis, and rule-based systems, each offering unique advantages in identifying and mitigating irregularities.

Related Work in Anomaly Detection
---------------------------------

Anomaly detection in blockchain networks has garnered significant attention in recent years, with researchers exploring various techniques to identify irregularities. Detecting anomalies is crucial for maintaining the security and integrity of blockchain systems, and numerous studies have proposed innovative methods to achieve this goal.

Machine learning algorithms, both supervised and unsupervised, have been widely used to detect anomalies in blockchain transactions. For instance, one study proposed a machine learning-based approach specifically designed for financial transactions, which can be effectively applied to blockchain data. This approach leverages labeled data to train models that can distinguish between normal and anomalous transactions.

In addition to machine learning, statistical analysis and network analysis have also been employed to identify unusual patterns in blockchain data. These methods analyze the structure and behavior of the network to spot deviations from expected norms. Deep learning techniques, which utilize neural networks with multiple layers, have further enhanced the ability to detect complex patterns and anomalies in large datasets.

A comprehensive survey of anomaly detection techniques for high-dimensional big data highlighted the challenges and limitations faced in blockchain networks. The survey emphasized the need for more accurate and efficient models capable of handling the complexity and volume of transaction data. As the field continues to evolve, ongoing research and development are essential to improve the effectiveness of anomaly detection in blockchain systems.

The importance of anomaly detection in blockchain
-------------------------------------------------

Cryptocurrencies have taken the world by storm, becoming a crucial component of the global financial system. As more individuals invest in these digital assets, the likelihood of encountering crypto anomalies increases. Crypto anomalies are unusual or abnormal behaviors in the cryptocurrency market that deviate from expected norms. Therefore, detecting these anomalies is vital and requires a deep understanding of market dynamics. Anomaly detection algorithms play a crucial role in identifying and mitigating malicious activities within blockchain systems. However, conventional anomaly detection methodologies face limitations, particularly with imbalanced datasets, as they struggle to accurately identify minority classes, such as anomalous [data points](https://www.coinapi.io/learn/glossary/data-points), due to their bias toward the majority class (normal data). These datasets often contain a majority of negative samples (non-malicious) and a minority of positive samples (malicious). This imbalance in negative and positive samples significantly impacts the performance of anomaly detection models, making it challenging to detect malicious activities accurately.

Methodology for Anomaly Detection
---------------------------------

The methodology for anomaly detection in blockchain involves several critical steps. It begins with data collection, where data is gathered from various sources such as blockchain transactions, network traffic, and system logs. This is followed by data preprocessing, which involves cleaning and transforming the data into a suitable format for analysis.

Random under-sampling techniques are used to address data imbalance issues, improving the performance of machine learning classifiers. Feature extraction is the next step, focusing on selecting relevant features from the data that can help identify anomalies. Model training then uses these features to train machine learning models.

Finally, model evaluation assesses the performance of these models using metrics like accuracy, precision, recall, and F1-score, ensuring they effectively detect anomalies while ensuring that the test data remains independent from the training data to avoid bias.

### Dataset for Anomaly Detection

The dataset used for anomaly detection in blockchain networks is a critical component of the analysis. Typically, such datasets include transaction data with details like transaction amounts, sender and receiver addresses, and timestamps. To provide a more holistic view of the blockchain network, additional features such as network traffic data and system logs may also be incorporated.

In our study, we utilized a dataset of Bitcoin transactions, which encompassed both normal and anomalous transactions. One of the primary challenges we faced was the highly imbalanced nature of the dataset, with the majority of transactions being normal and only a small fraction classified as anomalous. This imbalance can significantly impact the performance of anomaly detection models, making it difficult to accurately identify anomalies.

To address this issue, we employed various techniques to balance the dataset. Undersampling techniques were used to reduce the number of normal transactions, while oversampling methods aimed to increase the instances of anomalous transactions. By generating synthetic data points, we were able to create a more balanced dataset, which in turn improved the performance of our anomaly detection models.

A well-prepared dataset is essential for the success of anomaly detection efforts. By ensuring that the dataset accurately represents both normal and anomalous data, we can develop more robust and reliable models capable of effectively detecting anomalies in blockchain networks.

Anomaly Detection Techniques
----------------------------

Several techniques can be employed for anomaly detection in blockchain. Scenarios involving anomaly detection, such as dealing with imbalanced datasets in Bitcoin transactions where illicit transactions are rare, present significant challenges for machine learning classifiers.

Supervised learning involves training models with labeled data to understand the relationship between input features and output labels. Unsupervised learning, on the other hand, uses unlabeled data to identify patterns and relationships without predefined labels.

Deep learning leverages neural networks with multiple layers to learn complex patterns in the data. Network analysis examines the structure and behavior of networks to spot unusual patterns or anomalies. Each technique offers unique insights and capabilities, making them valuable tools in the arsenal for detecting anomalies in blockchain systems.

The stacked ensemble method differs from traditional ensemble methods by combining models using different algorithms and/or hyperparameters, enhancing model diversity and overall performance.

Axyon AI's challenges in anomaly detection algorithms
-----------------------------------------------------

Axyon AI, a fintech company that brings asset managers to the future with superior & accurate AI predictive solutions, faced several challenges in detecting crypto anomalies. It is crucial to use customized sampling techniques before training classification models to effectively balance the dataset and improve classifier performance, particularly when positive cases are scarce.

Over-sampling techniques, such as generating artificial data based on both majority and minority samples, were employed to address this issue. Additionally, random under-sampling techniques were used to tackle data imbalance, improving true positive rates while managing false positive rates.

Firstly, they lacked reliable, high-quality sources of historical and real-time [cryptocurrency data](https://www.coinapi.io/blog/how-to-get-historical-and-real-time-crypto-data). Secondly, they struggled with the lack of [aggregated data](https://www.coinapi.io/learn/glossary/aggregated-data), forcing them to collect information from multiple sources manually. As a result, this time-consuming process required expertise and hindered their ability to quickly detect anomalies.

Exploratory data analysis (EDA) is a crucial step in understanding the highly imbalanced nature of the dataset and identifying anomalies, guiding feature selection for machine learning classification.

Results Analysis and Evaluation
-------------------------------

Evaluating the results of anomaly detection in blockchain involves using various metrics to measure model performance. Accuracy indicates the proportion of correctly classified instances, while precision measures the proportion of true positives among all positive predictions.

Recall assesses the proportion of true positives among all actual positive instances, and the F1-score provides a harmonic mean of precision and recall. Visualization techniques like ROC curves and precision-recall curves can also be used to evaluate model performance, offering a graphical representation of the trade-offs between different metrics.

These evaluations ensure that the anomaly detection models are both effective and reliable. Additionally, the test data must remain independent from the training data to ensure unbiased model evaluation and maintain methodological rigor.

Explainability Analysis for Anomaly Detection
---------------------------------------------

Explainability analysis is a crucial aspect of anomaly detection in blockchain, as it helps stakeholders understand the decisions made by machine learning models. Techniques such as feature importance, partial dependence plots, and SHAP values are used to analyze the contribution of each feature to the predicted output.

Feature importance measures how much each feature influences the model, while partial dependence plots show the relationship between a specific feature and the predicted output. SHAP values provide a detailed view of each feature’s contribution to the model’s predictions.

These explainability techniques help identify the most important features contributing to anomalies and offer insights into the decision-making process of the models, enhancing trust and transparency.

CoinAPI's Market Data API: The solution
---------------------------------------

To address these challenges, Axyon AI turned to CoinAPI’s Market Data [API for Crypto](https://www.coinapi.io/) Anomaly Detection. Scenarios involving anomaly detection, such as dealing with imbalanced datasets in Bitcoin transactions where illicit transactions are rare, present significant challenges for machine learning classifiers.

Combined sampling methods have proven effective in improving classification metrics such as True Positive Rates (TPR) and False Positive Rates (FPR). By utilizing CoinAPI’s dependable data, Axyon AI developed efficient machine-learning models that promptly alerted clients about potential disturbances or abnormal behavior.

Combined sampling methods SMOTE played a crucial role in addressing imbalanced datasets, particularly in the context of Bitcoin transactions. The importance of combined sampling techniques in maximizing detection rates while minimizing false positives cannot be overstated.

Moreover, CoinAPI provided Axyon AI with comprehensive, reliable coverage of cryptocurrency markets, allowing them to generate synthetic data points to balance classes in imbalanced datasets.

The benefits of partnering with CoinAPI
---------------------------------------

Partnering with CoinAPI has been a game-changer for Axyon AI. By leveraging established under-sampling techniques, they have been able to balance datasets effectively, particularly in the context of anomaly detection and fraud identification.

Consequently, the fintech company has established a strong relationship with its cryptocurrency clients. Furthermore, CoinAPI’s top-notch market data has saved Axyon AI valuable time and resources, allowing it to focus on enhancing its anomaly detection solution and AI models for business expansion.

Additionally, over-sampling methods aim to increase the number of instances in the minority class, which has complemented their use of under-sampling techniques. CoinAPI’s flexible and easy-to-integrate API has made it convenient for Axyon AI to access and analyze market data tailored to their specific needs. As a result, this has further streamlined their processes and improved their efficiency in detecting crypto anomalies.

#### Join us and discover an API tailored to your needs with combined sampling methods. Test your use case and see if CoinAPI fits your product. [Click here to test our API!](https://www.coinapi.io/contact-us)

![background](https://cdn.sanity.io/images/o65xz72l/production/e8a6b2e74f8d4106aca6ea9739a663190aadf694-40x40.svg)

Stay up-to-date with the latest CoinApi News.

Send

By subscribing to our newsletter, you accept our website terms and privacy policy.

### Recent Articles

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F1c608fa1f94b18e18e30a04e3006c5455b4dfeca-1000x500.png&w=3840&q=75)

Product Features

How to Get Accurate Historical Token Price Data for Financial Reporting

Retrieve complete, audit-ready historical token price data with CoinAPI. Perfect for finance managers, controllers, and ops teams handling Web3 assets.](/blog/historical-token-price-data-financial-reporting)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fabe93ecc9d8dfb15701c7ab459b916701aaf13e1-1000x500.png&w=3840&q=75)

Crypto Knowledge

Spot Trading in Crypto: What It Is, How It Works, and How to Master It

Learn spot trading in crypto from basics to pro strategies. Understand bids, asks, order books & use CoinAPI’s real-time and historical data.](/blog/spot-trading-in-crypto-guide)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ffee6e77e8c599cbdc3e536317ac7adcbbbb59f5e-1000x500.png&w=3840&q=75)

Crypto Knowledge

Understanding Crypto Market Data: From Tick Trades to OHLCV and Order Books

Choose the right crypto market data type - tick trades, quotes, order books, or OHLCV—for trading success. Complete guide with examples and use cases. Focus keyphrase: crypto market data](/blog/understanding-crypto-market-data-tick-trades-ohlcv-order-books)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F8c92ab519a2ec5af8b7edc3ba2371d9243750cc7-1000x500.png&w=3840&q=75)

Product Features

Crypto Tax Made Simple: How CoinAPI Exchange Rates Power Accurate Accounting

Solve crypto tax compliance with professional exchange rates API. Get audit-ready historical pricing, eliminate capital gains errors, and standardize crypto pricing across exchanges.](/blog/crypto-tax-coinapi-exchange-rates)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fa7ddd03200081ffce3dfdd9d9bc805c4cbac5801-1000x500.png&w=3840&q=75)

Crypto Knowledge

What Everyone Gets Wrong About L3 Data in Crypto

L3 data in crypto gives you full visibility into every individual order — but most traders use it wrong. Learn how to read L3 correctly, avoid common pitfalls, and scale smarter with CoinAPI.](/blog/what-everyone-gets-wrong-about-l3-data-in-crypto)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fab2a315d6528b49cda3fd200b418af97ce48894f-1000x500.png&w=3840&q=75)

Crypto Knowledge

How Level 3 Market Data Transforms Trading Performance

What if you could see every individual order placement, modification, and cancellation happening in real-time across crypto exchanges? Most traders operate blindfolded with basic price feeds, while sophisticated institutions access Level 3 market data—granular, order-by-order intelligence that reveals market microstructure 99% of traders never see.](/blog/how-level-3-market-data-transforms-trading-performance)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2F47694398be69f125e8bc4fcd68c23cba8ad4f7e2-1000x500.png&w=3840&q=75)

Product Features

Pros and Cons of JSON-RPC and REST APIs Protocols

Choose the right API protocol for crypto trading. Compare JSON-RPC vs REST for market data, trading bots, and DeFi applications with real performance benchmarks.](/blog/pros-and-cons-of-json-rpc-and-rest-apis-protocols)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Ff4583e287f8949afaddc3a4aaf89091f834a8bd6-1000x500.png&w=3840&q=75)

Use case

Exchange Rates API for Fast Historical Token Prices

Exchange rates API for finance managers at Web3 companies. Get fast historical closing prices, multiple symbols per call, and ISO timestamps for compliance.](/blog/exchange-rates-api-for-fast-historical-token-prices)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fecfd635f082d4e6a312b9312725cf195c5d9dccd-1000x500.png&w=3840&q=75)

Crypto Knowledge

Why Crypto to Fiat APIs Are Revolutionizing Financial Operations

Discover how crypto-to-fiat APIs solve critical business challenges in portfolio management, tax compliance, and financial reporting. Learn why leading finance teams are standardizing on professional-grade solutions.](/blog/why-crypto-to-fiat-apis-are-revolutionizing-financial-operations)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fe7526651c2ce24101581e90a5982c62bb1b84f18-1000x500.png&w=3840&q=75)

Product Features

Metrics API V2: Trading Volume Analysis and On-Chain Metrics

Most crypto APIs show you prices on exchanges. But that’s only half the story. CoinAPI’s new Metrics API V2 gives you real-time visibility into DeFi protocols, stablecoin flows, and cross-chain activity — the $200B+ blind spot in traditional market data. With sub-30 second updates, standardized metrics, and multi-chain coverage, it's the fastest way to unlock on-chain trading signals, measure TVL, and track stablecoin health. If you’re still trading without it, you're flying blind.](/blog/metrics-api-v2-trading-volume-analysis-and-on-chain-metrics)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fb5471406ca9cbf8f906574131747c4233f29e240-1000x500.png&w=3840&q=75)

Product Features

Crypto Data Download: The Flat Files Advantage

Discover how to download crypto data for free and access premium bulk historical datasets. Compare APIs, learn S3 methods, and start backtesting with terabytes of clean cryptocurrency market data.](/blog/crypto-data-download-the-flat-files-advantage)

[![background](/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Fo65xz72l%2Fproduction%2Fca54fa639768f18864c62215de750ec797f31ddd-1000x500.png&w=3840&q=75)

Product Features

Why WebSocket Multiple Updates Beat REST APIs for Real-Time Crypto Trading

Learn why WebSocket multiple updates for crypto trading APIs provide faster signals than single response data. Discover real-time OHLCV implementation strategies for Bitcoin and cryptocurrency market data.](/blog/why-websocket-multiple-updates-beat-rest-apis-for-real-time-crypto-trading)

### Crypto API made simple: Try now or speak to our sales team

[Start for Free](/market-data-api/pricing)[Get in Touch](/contact-us)

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