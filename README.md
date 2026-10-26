# Bank Indonesia Exchange Rates API — bank-indonesia-exchange-rate

[![npm version](https://img.shields.io/npm/v/bank-indonesia-exchange-rate.svg)](https://www.npmjs.com/package/bank-indonesia-exchange-rate)
[![license](https://img.shields.io/npm/l/bank-indonesia-exchange-rate.svg)](https://github.com/AllRates-Today/bank-indonesia-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/bank-indonesia-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/IDR today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbi%3Fsource%3DUSD%26target%3DIDR&query=%24.rate&label=USD%2FIDR%20published%20by%20Bank%20Indonesia&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bi/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbi%3Fsource%3DUSD%26target%3DIDR&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bi/)

**Official Bank Indonesia (Indonesia) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Bank Indonesia itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Bank Indonesia's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2016** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Bank Indonesia itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## ⚡ Try it without a key

The latest Bank Indonesia table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/bi?source=USD&target=IDR"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/bi').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only (JSON by default; add `?format=csv`, `xml` or `xlsx` for a file) and is free to use with a visible, followable link where the rates are shown: `<a href="https://allratestoday.com">Exchange rates by AllRatesToday</a>` (terms: <https://allratestoday.com/terms/#attribution>). The client below uses the keyed API, which adds point-in-time tables and history; with a key the link is appreciated, not required.

## 📈 Latest published table

[![Latest Bank Indonesia table](https://allratestoday.com/api/open/central-bank/bi/table.svg)](https://allratestoday.com/central-bank-rates-api/bi/)

The image is rendered live from the keyless endpoint above, so it follows the central bank's publications on npm and on GitHub alike without a new release. The same table as text is folded below for search and copy-paste: on GitHub [a daily Action](.github/workflows/daily-table.yml) refreshes it whenever the central bank publishes a new table; on npm it is as of the package's publish date.

<!-- daily-table:start -->
<details>
<summary>Table as text: published 2026-10-26 by Bank Indonesia — 50 rates. Updated 2026-10-26.</summary>

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AUD | IDR | buy | 12617.42 |
| AUD | IDR | sell | 12747.86 |
| BND | IDR | buy | 14064.5 |
| BND | IDR | sell | 14206.97 |
| CAD | IDR | buy | 12829.98 |
| CAD | IDR | sell | 12960.78 |
| CHF | IDR | buy | 21847.92 |
| CHF | IDR | sell | 22075.55 |
| CNH | IDR | buy | 2694.96 |
| CNH | IDR | sell | 2722.09 |
| CNY | IDR | buy | 2694.92 |
| CNY | IDR | sell | 2722.3 |
| DKK | IDR | buy | 2693.11 |
| DKK | IDR | sell | 2720.62 |
| EUR | IDR | buy | 20128.9 |
| EUR | IDR | sell | 20338.47 |
| GBP | IDR | buy | 24046.44 |
| GBP | IDR | sell | 24293.58 |
| HKD | IDR | buy | 2292.79 |
| HKD | IDR | sell | 2315.95 |
| JPY | IDR | buy | 114.5283 |
| JPY | IDR | sell | 115.7089 |
| KRW | IDR | buy | 13.56 |
| KRW | IDR | sell | 13.69 |
| KWD | IDR | buy | 58362.77 |
| KWD | IDR | sell | 58968.5 |
| LAK | IDR | buy | 0.8 |
| LAK | IDR | sell | 0.81 |
| MYR | IDR | buy | 4398.98 |
| MYR | IDR | sell | 4447.55 |
| NOK | IDR | buy | 1923.26 |
| NOK | IDR | sell | 1945.09 |
| NZD | IDR | buy | 10224.46 |
| NZD | IDR | sell | 10330.85 |
| PGK | IDR | buy | 3867.21 |
| PGK | IDR | sell | 4214.79 |
| PHP | IDR | buy | 282.48 |
| PHP | IDR | sell | 285.74 |
| SAR | IDR | buy | 4789.96 |
| SAR | IDR | sell | 4838.62 |
| SEK | IDR | buy | 1810.17 |
| SEK | IDR | sell | 1828.61 |
| SGD | IDR | buy | 14063.4 |
| SGD | IDR | sell | 14208.08 |
| THB | IDR | buy | 532.23 |
| THB | IDR | sell | 538.21 |
| USD | IDR | buy | 17978.65 |
| USD | IDR | sell | 18159.35 |
| VND | IDR | buy | 0.7 |
| VND | IDR | sell | 0.7 |

</details>

Source: [Official rates published by BI, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/bi/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 📦 Installation

```bash
npm install bank-indonesia-exchange-rate
```

```bash
yarn add bank-indonesia-exchange-rate
```

```bash
pnpm add bank-indonesia-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/bank-indonesia-exchange-rate`](https://www.npmjs.com/package/@allratestoday/bank-indonesia-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'bank-indonesia-exchange-rate';

const pair = await getRate('USD', 'IDR', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Bank Indonesia rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'IDR', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'bi',
  name: 'Bank Indonesia',
  rate_date: '2026-10-14',   // Bank Indonesia's own publication date
  source: 'USD',
  target: 'IDR',
  rate: 18019.65,
  rate_type: 'sell',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'bank-indonesia-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'bi',
  name: 'Bank Indonesia',
  rate_date: '2026-10-14',
  rates: [
    { "base": "USD", "quote": "IDR", "type": "sell", "value": 18019.65 },
    { "base": "USD", "quote": "IDR", "type": "buy", "value": 17840.35 },
    // … the rest of the published table (25 currencies vs IDR)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2016 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'bank-indonesia-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'IDR' });
```

**Response:**

```javascript
{
  bank: 'bi',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'bank-indonesia-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'IDR', from: '2026-01-01', to: '2026-10-14' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'bi',
  source: 'USD',
  target: 'IDR',
  from: '2026-01-01',
  to: '2026-10-14',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-14', rate: 18019.65, rate_type: 'sell', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Bank Indonesia currently publishes rates covering **25 currencies** against the IDR (as of the latest table):

🇦🇺 `AUD` · 🇧🇳 `BND` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNH` · 🇨🇳 `CNY` · 🇩🇰 `DKK` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇭🇰 `HKD` · 🇯🇵 `JPY` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇱🇦 `LAK` · 🇲🇾 `MYR` · 🇳🇴 `NOK` · 🇳🇿 `NZD` · 🇵🇬 `PGK` · 🇵🇭 `PHP` · 🇸🇦 `SAR` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇹🇭 `THB` · 🇺🇸 `USD` · 🇻🇳 `VND`

## 🏛️ Source

Bank Indonesia is the central bank of the Republic of Indonesia. It publishes transaction reference rates (buy and sell) for the rupiah against major currencies once each business day — the standard reference for statutory and tax purposes in Indonesia.

- Publisher's own page: [BI transaction rates](https://www.bi.go.id/en/statistik/informasi-kurs/transaksi-bi/default.aspx) · [www.bi.go.id](https://www.bi.go.id)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Bank Indonesia rates page](https://allratestoday.com/central-bank-rates-api/bi/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Bank Indonesia quotes **IDR per 1 unit of foreign currency** (e.g. `base: "USD", quote: "IDR"` means IDR per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`sell` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Bank Indonesia rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/bi/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('bi')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate bi ...` command
- Evaluating? Agents can self-issue a trial key with no signup: `POST https://allratestoday.com/api/agent/keys` (send `Content-Type: application/json`) returns a 100-call key valid 7 days that covers the free-plan methods (latest table, pairs); dated tables and history need a [paid plan](https://allratestoday.com/pricing/). The MCP servers expose it as `request_trial_key`
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Bank Indonesia does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via IDR from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Bank Indonesia |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'bank-indonesia-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('bank-indonesia-exchange-rate');

getRate('USD', 'IDR', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2016 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRatesToday/central-bank-exchange-rates](https://huggingface.co/datasets/AllRatesToday/central-bank-exchange-rates) — one CSV per institution (`rates/bi.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- Raw JSON on GitHub: `https://raw.githubusercontent.com/AllRates-Today/central-bank-exchange-rates/main/data/bi/latest.json`

## 🔗 Links

- [Bank Indonesia rates page](https://allratestoday.com/central-bank-rates-api/bi/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/bank-indonesia-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (Free)](https://allratestoday.com/register) · [Dashboard](https://allratestoday.com/profile) · [Pricing](https://allratestoday.com/pricing/)
- [Status](https://allratestoday.com/status)
- [Postman collection](https://allratestoday.com/postman/)
- [GitHub](https://github.com/AllRates-Today/bank-indonesia-exchange-rate)

## 📜 License

MIT
