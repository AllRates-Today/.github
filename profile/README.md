## AllRatesToday — Exchange Rate APIs for Developers and Compliance Teams

[![Powered by AllRatesToday](https://img.shields.io/badge/Powered%20by-AllRatesToday-orange.svg)](https://allratestoday.com)
[![API Status](https://img.shields.io/badge/API-Online-brightgreen)](https://allratestoday.com/status)
[![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/AllRates-Today/exchange-rates-api/blob/main/LICENSE)

**AllRatesToday** serves two kinds of exchange rate, because reporting and pricing need different numbers:

- **Mid-market rates** for 160+ currencies — sourced from institutional interbank market data, fetched live on every request, no markup and no spread.
- **Official published rates** from **100+ central banks and tax authorities** (102 central banks, 4 tax authorities) — the fixed, citable numbers that tax filings, customs declarations, audits, and compliant invoicing require.

## 🏁 Quick start — no key needed

Every central bank's latest table is open, CORS-enabled and edge-cached. No sign-up.

```bash
curl "https://allratestoday.com/api/open/central-bank/ecb?source=EUR&target=USD"
```

The same tables, with full history, are plain files on a CDN:

```
https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/ecb/latest.json
https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/hmrc/history/2026.csv
```

→ [**central-bank-exchange-rates**](https://github.com/AllRates-Today/central-bank-exchange-rates) — 100+ institutions as daily JSON and CSV, refreshed four times a day.

Real-time mid-market rates for 160+ currencies take a free API key ([get one](https://allratestoday.com/register), no credit card):

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
  "https://allratestoday.com/api/v1/rates?source=USD&target=EUR,GBP,JPY"
```

## 🚀 Starter templates

Click **Use this template** and you have a working app in a minute. All of them run keyless on official rates.

| Template | Stack |
|---|---|
| [nextjs-currency-starter](https://github.com/AllRates-Today/nextjs-currency-starter) | Next.js 15 App Router, server-side key for live rates |
| [react-currency-converter](https://github.com/AllRates-Today/react-currency-converter) | React + Vite, browser only |
| [python-currency-cli](https://github.com/AllRates-Today/python-currency-cli) | Python 3.9+, zero dependencies, `currency convert 100 USD EUR` |
| [google-sheets-exchange-rates](https://github.com/AllRates-Today/google-sheets-exchange-rates) | Apps Script: `=CBRATE("ecb","USD")` |
| [central-bank-rates-demo](https://github.com/AllRates-Today/central-bank-rates-demo) | Static site on GitHub Pages using every per-bank SDK |

## 🏦 Central Bank Rates API

Tax filings, customs declarations, audits, statutory accounts and invoicing rules in most countries don't ask what the market said — they require **the official rate published by the central bank** for a given date. That number is fixed, citable, and never changes after publication. This API serves those tables.

**102 central banks and 4 tax authorities**, over **8 million published rates**, the oldest reaching back to **1914**.

```bash
# The ECB's latest published table — one pair from it
curl -H "Authorization: Bearer YOUR_API_KEY" \
  "https://allratestoday.com/api/v1/central-bank/ecb/latest?source=EUR&target=USD"
```

```json
{
  "bank": "ecb",
  "rate_date": "2026-08-12",
  "source": "EUR",
  "target": "USD",
  "rate": 1.1545,
  "rate_type": "reference",
  "derived": false,
  "method": "published"
}
```

### Endpoints

| Endpoint | Returns |
|----------|---------|
| `/api/v1/central-banks` | Every covered source — home currency, rate types, latest date, depth of history |
| `/api/v1/central-bank/{bank}/latest` | The bank's most recent published table — free tier included |
| `/api/v1/central-bank/{bank}/{YYYY-MM-DD}` | The official table in force on that date |
| `/api/v1/central-bank/{bank}/history` | Daily series for one pair over a date range |
| `/api/v1/central-bank/{bank}/availability` | Which dates the bank actually published |

Every endpoint also speaks `?format=csv`, `xml` and `xlsx` — the spreadsheet an auditor asks for, without a conversion step.

### What makes it usable for compliance

- **The institution's own publication date on every response**, not the date you asked for. Request a weekend or a holiday and you get the table that was legally in force, flagged with `published_on_requested_date: false`.
- **Nothing silently invented.** Pairs a bank does not print directly are cross-computed from its own table and flagged `derived`, so an official rate is never confused with one we calculated.
- **Deep archives**, not just the last few years: the SNB series reaches 1914, the Bank of Korea 1964, the HKMA 1981, the ECB 1999, the Central Bank of Kuwait 2008 across its full 134-currency board.
- **One key, one quota, one bill** — central bank calls count the same as any other request, and the free tier covers latest tables.

### Coverage

The ECB, US Federal Reserve (H.10), Bank of England, People's Bank of China, Reserve Bank of India, Bank of Canada, Bank of Japan, Swiss National Bank, Central Bank of Sri Lanka and 90 more — with a deliberate focus on the South and Southeast Asian, African and Latin American central banks other providers skip. For tax work: HM Revenue & Customs, the US Treasury and Swiss customs (BAZG).

Every covered source also has a dedicated zero-dependency npm package hosted in this org — [`ecb-exchange-rate`](https://github.com/AllRates-Today/ecb-exchange-rate), [`fed-exchange-rate`](https://github.com/AllRates-Today/fed-exchange-rate), [`cbsl-exchange-rate`](https://github.com/AllRates-Today/cbsl-exchange-rate), [`rbi-exchange-rate`](https://github.com/AllRates-Today/rbi-exchange-rate) and 100 more — plus matching PyPI packages.

- Central bank coverage & per-bank docs: [allratestoday.com/central-bank-rates-api](https://allratestoday.com/central-bank-rates-api/)
- Tax authority coverage: [allratestoday.com/tax-authority-rates-api](https://allratestoday.com/tax-authority-rates-api/)
- How the rates are sourced and composites computed: [official rates methodology](https://allratestoday.com/official-rates-methodology/)

## 📦 Official SDKs

| Language | Package | Install |
|----------|---------|---------|
| **JavaScript/TypeScript** | [@allratestoday/sdk](https://www.npmjs.com/package/@allratestoday/sdk) | `npm i @allratestoday/sdk` |
| **Python** | [allratestoday](https://pypi.org/project/allratestoday/) | `pip install allratestoday` |
| **PHP** | [allratestoday/sdk](https://packagist.org/packages/allratestoday/sdk) | `composer require allratestoday/sdk` |
| **Go** | [allratestoday-go](https://github.com/AllRates-Today/allratestoday-go) | `go get github.com/AllRates-Today/allratestoday-go` |
| **Rust** | [allratestoday](https://crates.io/crates/allratestoday) | `cargo add allratestoday` |
| **React** | [react-currency-localizer-realtime](https://www.npmjs.com/package/react-currency-localizer-realtime) | `npm i react-currency-localizer-realtime` |

## 🤖 AI & MCP integrations

- [**mcp-server**](https://github.com/AllRates-Today/mcp-server) — MCP server for Claude Code, Cursor, Claude Desktop, and Windsurf
- [**central-bank-mcp**](https://github.com/AllRates-Today/central-bank-mcp) — official central-bank and tax-authority rates for AI agents, keyless
- [**claude-code-plugin**](https://github.com/AllRates-Today/claude-code-plugin) — Claude Code plugin, no API key needed
- [**realtime-exchange-rate-mcp**](https://github.com/AllRates-Today/realtime-exchange-rate-mcp) — Realtime FX rates MCP server
- [**currency-agent**](https://github.com/AllRates-Today/currency-agent) — Currency agent sample built on A2A, Google ADK and MCP
- [**allratestoday-deepseek**](https://github.com/AllRates-Today/allratestoday-deepseek) — DeepSeek function-calling tools

## 🧰 Developer tools

- [**fx-rates**](https://github.com/AllRates-Today/fx-rates) — Lightweight Node.js library & CLI for exchange rates
- [**moneyify**](https://github.com/AllRates-Today/moneyify) — Currency conversion library, cashify-compatible
- [**live-currency-converter**](https://github.com/AllRates-Today/live-currency-converter) — Free live currency converter
- [**central-bank-rates-demo**](https://github.com/AllRates-Today/central-bank-rates-demo) — Live demo exercising every per-bank SDK

## 🔗 Links

[Website](https://allratestoday.com) | [Exchange Rate API](https://allratestoday.com/exchange-rate-api/) | [Currency API](https://allratestoday.com/currency-api/) | [API Docs](https://allratestoday.com/docs) | [API Reference](https://allratestoday.com/api-reference/) | [Central Bank Rates](https://allratestoday.com/central-bank-rates-api/) | [Tax Authority Rates](https://allratestoday.com/tax-authority-rates-api/) | [Get Free API Key](https://allratestoday.com/register) | [Status](https://allratestoday.com/status) | [Discord](https://discord.gg/7dyhYhC6)
