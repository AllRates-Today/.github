## AllRatesToday — Exchange Rate APIs for Developers and Compliance Teams

[![Powered by AllRatesToday](https://img.shields.io/badge/Powered%20by-AllRatesToday-orange.svg)](https://allratestoday.com)
[![API Status](https://img.shields.io/badge/API-Online-brightgreen)](https://allratestoday.com/status)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/AllRates-Today/exchange-rates-api/blob/main/LICENSE)

**AllRatesToday** serves two kinds of exchange rate, because reporting and pricing need different numbers:

- **Mid-market rates** for 160+ currencies — sourced from institutional interbank market data, fetched live on every request, no markup and no spread.
- **Official published rates** from **54 central banks and 3 national tax authorities** — the fixed, citable numbers that tax filings, customs declarations, audits, and compliant invoicing require.

## 🏁 Quick start

Every endpoint takes an API key. [Get a free one](https://allratestoday.com/register) — no credit card.

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
  "https://allratestoday.com/api/v1/rates?source=USD&target=EUR,GBP,JPY"
```

## 🏦 Official central bank & tax authority rates

The daily tables published by the ECB, the US Federal Reserve (H.10), the Bank of England, the People's Bank of China, the Reserve Bank of India, the Bank of Canada, the Central Bank of Sri Lanka and 47 more — plus HM Revenue & Customs, the US Treasury and Swiss customs (BAZG) for tax work. Served as clean JSON, CSV, XML or XLSX, with the institution's own publication date on every response and history reaching back to 1999 for some sources.

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
  "https://allratestoday.com/api/v1/central-bank/ecb/latest?source=USD&target=EUR"
```

Pairs an institution does not print directly are computed from its own table and explicitly flagged `derived`, so an official rate is never confused with one we calculated.

Every covered source also has a dedicated zero-dependency npm package hosted in this org — [`ecb-exchange-rate`](https://github.com/AllRates-Today/ecb-exchange-rate), [`fed-exchange-rate`](https://github.com/AllRates-Today/fed-exchange-rate), [`cbsl-exchange-rate`](https://github.com/AllRates-Today/cbsl-exchange-rate), [`rbi-exchange-rate`](https://github.com/AllRates-Today/rbi-exchange-rate) and 50 more.

- Central bank coverage & per-bank docs: [allratestoday.com/central-bank-rates-api](https://allratestoday.com/central-bank-rates-api/)
- Tax authority coverage: [allratestoday.com/tax-authority-rates-api](https://allratestoday.com/tax-authority-rates-api/)

## 📦 Official SDKs

| Language | Package | Install |
|----------|---------|---------|
| **JavaScript/TypeScript** | [@allratestoday/sdk](https://www.npmjs.com/package/@allratestoday/sdk) | `npm i @allratestoday/sdk` |
| **Python** | [allratestoday](https://pypi.org/project/allratestoday/) | `pip install allratestoday` |
| **PHP** | [allratestoday/sdk](https://packagist.org/packages/allratestoday/sdk) | `composer require allratestoday/sdk` |
| **Rust** | [allratestoday](https://crates.io/crates/allratestoday) | `cargo add allratestoday` |
| **React** | [react-currency-localizer-realtime](https://www.npmjs.com/package/react-currency-localizer-realtime) | `npm i react-currency-localizer-realtime` |

## 🤖 AI & MCP integrations

- [**mcp-server**](https://github.com/AllRates-Today/mcp-server) — MCP server for Claude Code, Cursor, Claude Desktop, and Windsurf
- [**realtime-exchange-rate-mcp**](https://github.com/AllRates-Today/realtime-exchange-rate-mcp) — Realtime FX rates MCP server
- [**currency-agent**](https://github.com/AllRates-Today/currency-agent) — Currency agent sample built on A2A, Google ADK and MCP
- [**allratestoday-deepseek**](https://github.com/AllRates-Today/allratestoday-deepseek) — DeepSeek function-calling tools

## 🧰 Developer tools

- [**fx-rates**](https://github.com/AllRates-Today/fx-rates) — Lightweight Node.js library & CLI for exchange rates
- [**moneyify**](https://github.com/AllRates-Today/moneyify) — Currency conversion library, cashify-compatible
- [**live-currency-converter**](https://github.com/AllRates-Today/live-currency-converter) — Free live currency converter
- [**central-bank-rates-demo**](https://github.com/AllRates-Today/central-bank-rates-demo) — Live demo exercising every per-bank SDK

## 🔗 Links

[Website](https://allratestoday.com) | [API Docs](https://allratestoday.com/docs) | [API Reference](https://allratestoday.com/api-reference/) | [Central Bank Rates](https://allratestoday.com/central-bank-rates-api/) | [Tax Authority Rates](https://allratestoday.com/tax-authority-rates-api/) | [Get Free API Key](https://allratestoday.com/register) | [Status](https://allratestoday.com/status) | [Discord](https://discord.gg/7dyhYhC6)
