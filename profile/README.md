## Free Exchange Rate API for 160+ Currencies

[![Powered by AllRatesToday](https://img.shields.io/badge/Powered%20by-AllRatesToday-orange.svg)](https://allratestoday.com)

[![API Status](https://img.shields.io/badge/API-Online-brightgreen)](https://allratestoday.com) [![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/AllRates-Today/exchange-rates-api/blob/main/LICENSE)

**AllRatesToday** provides accurate, real-time and historical currency exchange rate data through a simple REST API — mid-market rates from institutional interbank market data, fetched live, no markup, no spread. Plus **official central-bank rates from 24 central banks** for tax, audit, and compliance work.

### Quick Start

Single-pair lookups are public — no API key needed:

```bash
curl "https://allratestoday.com/api/rate?source=USD&target=EUR"
```

```json
{ "rate": 0.92145, "source": "interbank" }
```

Multi-target and historical data with a free API key:

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
  "https://allratestoday.com/api/v1/rates?source=USD&target=EUR,GBP,JPY"
```

### Official Central Bank Rates

The official daily tables published by **24 central banks** — ECB, US Federal Reserve (H.10), Bank of England, People's Bank of China, Reserve Bank of India, Bank of Canada, Central Bank of Sri Lanka, and more — served as clean JSON (or CSV) with the bank's own publication date on every response. History back to 1999 for some banks. These are the fixed, citable rates that tax filings, customs, audits, and compliant invoicing require.

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
  "https://allratestoday.com/api/v1/central-bank/ecb/latest?source=USD&target=EUR"
```

Each covered bank also has a dedicated zero-dependency npm package hosted in this org — [`ecb-exchange-rate`](https://github.com/AllRates-Today/ecb-exchange-rate), [`fed-exchange-rate`](https://github.com/AllRates-Today/fed-exchange-rate), [`cbsl-exchange-rate`](https://github.com/AllRates-Today/cbsl-exchange-rate), [`rbi-exchange-rate`](https://github.com/AllRates-Today/rbi-exchange-rate), and 20 more. Coverage map and per-bank docs: [allratestoday.com/central-bank-rates-api](https://allratestoday.com/central-bank-rates-api/)

### Official SDKs

| Language | Package | Install |
|----------|---------|---------|
| **JavaScript/TypeScript** | [@allratestoday/sdk](https://www.npmjs.com/package/@allratestoday/sdk) | `npm i @allratestoday/sdk` |
| **Python** | [allratestoday](https://pypi.org/project/allratestoday/) | `pip install allratestoday` |
| **PHP** | [allratestoday/sdk](https://packagist.org/packages/allratestoday/sdk) | `composer require allratestoday/sdk` |
| **Rust** | [allratestoday](https://crates.io/crates/allratestoday) | `cargo add allratestoday` |
| **React** | [@allratestoday/react](https://www.npmjs.com/package/@allratestoday/react) | `npm i @allratestoday/react` |

### AI & MCP Integrations

- [**mcp-server**](https://github.com/AllRates-Today/mcp-server) — MCP server for Claude Code, Cursor, Claude Desktop, and Windsurf
- [**realtime-exchange-rate-mcp**](https://github.com/AllRates-Today/realtime-exchange-rate-mcp) — Realtime FX rates MCP server
- [**allratestoday-deepseek**](https://github.com/AllRates-Today/allratestoday-deepseek) — DeepSeek function-calling tools

### Developer Tools

- [**fx-rates**](https://github.com/AllRates-Today/fx-rates) — Lightweight Node.js library & CLI for exchange rates
- [**moneyify**](https://github.com/AllRates-Today/moneyify) — Currency conversion library, cashify-compatible
- [**live-currency-converter**](https://github.com/AllRates-Today/live-currency-converter) — Free live converter for 200+ currencies

### Links

[Website](https://allratestoday.com) | [API Docs](https://allratestoday.com/docs) | [API Reference](https://allratestoday.com/api-reference/) | [Central Bank Rates](https://allratestoday.com/central-bank-rates-api/) | [Get Free API Key](https://allratestoday.com/register) | [Discord](https://discord.gg/7dyhYhC6)
