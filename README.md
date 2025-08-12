# llms-md

A curated, offline collection of Markdown documentation and website content for CoinAPI and FinFeedAPI. The repository mirrors content from multiple domains and organizes it by source.

## Repository structure

- `docs.coinapi.io/`: Developer documentation for CoinAPI products and services.
  - Includes: EMS API, Exchange Rates API, Flat Files API, Indexes API, Market Data, NAAS API, general guides, and how-to content.
- `docs.finfeedapi.com/`: Developer documentation for FinFeedAPI.
  - Includes: Currencies API, Market Data, SEC API, Stock API, general guides.
- `www.coinapi.io/`: Public website content for CoinAPI.
  - Includes: Blog, case studies, learn glossary, products, pricing, legal, and use cases.
- `www.finfeedapi.com/`: Public website content for FinFeedAPI.
  - Includes: Blog, learn, products, use cases, and legal.

Common helper files found under multiple roots:

- `llms.txt` and `llms-full.txt`: Consolidated plain-text exports of the Markdown content for use in search, indexing, or LLM training/evaluation.

## How to use

- Browse locally with any Markdown viewer or IDE preview.
- Full-text search the repo (e.g., ripgrep) to locate topics across products and sites.
- The structure mirrors the original sites; paths generally correspond to the original URLs.

## Notes

- This repository is read-only documentation content. There is no build system or code to run.
- File counts shown in some directories are informational summaries; the actual content is the Markdown files.

## License

Content ownership belongs to the respective original publishers (CoinAPI, FinFeedAPI). This repository is provided for internal/reference purposes.
