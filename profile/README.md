## Free Exchange Rate API for 160+ Currencies

[![API Status](https://img.shields.io/badge/API-Online-brightgreen)](https://allratestoday.com) [![License](https://img.shields.io/badge/license-MIT-blue)](https://github.com/AllRates-Today/exchange-rates-api/blob/main/LICENSE)

**AllRatesToday** provides accurate, real-time and historical currency exchange rate data through a simple REST API. Mid-market rates updated every 60 seconds, no markup, no spread.

### Quick Start

```bash
curl "https://api.allratestoday.com/v1/latest?base=USD&symbols=EUR,GBP,JPY"
```

```json
{
  "base": "USD",
  "rates": { "EUR": 0.9234, "GBP": 0.7891, "JPY": 149.52 }
}
```

### Official SDKs

| Language | Package | Install |
|----------|---------|---------|
| **JavaScript/TypeScript** | [@allratestoday/sdk](https://www.npmjs.com/package/@allratestoday/sdk) | `npm i @allratestoday/sdk` |
| **Python** | [allratestoday](https://pypi.org/project/allratestoday/) | `pip install allratestoday` |
| **PHP** | [allratestoday/sdk](https://packagist.org/packages/allratestoday/sdk) | `composer require allratestoday/sdk` |
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

[Website](https://allratestoday.com) | [API Docs](https://allratestoday.com/docs) | [Get Free API Key](https://allratestoday.com/register) | [Discord](https://discord.gg/7dyhYhC6)
