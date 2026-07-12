# Barchart (barchart)

Barchart is a leading provider of market data and commodity data, delivering real-time, delayed, and historical financial and reference data across equities, futures, options, forex, cryptocurrencies, ETFs, mutual funds, indexes, and physical commodities. The Barchart OnDemand API is a commercially licensed REST service hosted at `ondemand.websol.barchart.com`, authenticated with an `apikey` query parameter and returning JSON, XML, or CSV (GET, POST, and SOAP are supported). It exposes a broad documented endpoint catalog — `getQuote`, `getHistory`, `getEquitiesByExchange`, `getFuturesOptions`, `getProfile`, `getCrypto`, `getGrainBids`, `getNews`, `getWeather`, and dozens more — covering quotes, historical time series, fundamentals, corporate actions, options analytics, agricultural and energy commodity data, technicals, and news.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/barchart/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/barchart/refs/heads/main/apis.yml)

## Access Model (Honest Note)

Barchart OnDemand is **subscription and enterprise gated**, not a free or open API. Every request requires a Barchart-issued `apikey`, provisioned through a subscription or custom enterprise agreement; a limited **free trial** key is available for evaluation. Real-time exchange data carries additional **exchange licensing fees** beyond the Barchart subscription, and some tiers serve delayed (up to ~20 minutes) or end-of-day data. Default result sets are capped at 20 records unless a `maxRecords` parameter is supplied.

The **endpoint names, HTTP method, `apikey` authentication, format suffixes, and request parameters** in this repository are accurate and drawn from Barchart's public OnDemand documentation. Because full response payloads and field catalogs are entitlement-specific and not published in machine-readable form, the OpenAPI **response schemas are honestly modeled** (`endpointsModeled: true`) rather than captured from live authenticated responses. Field sets returned depend on your Barchart data license.

Barchart maintains open-source **client** libraries on GitHub (e.g. `barchart-ondemand-client-js`), but the data service itself is proprietary.

## Tags

- Market Data
- Financial Data
- Commodities
- Futures
- Options
- Reference Data
- Equities
- Historical Data
- Cryptocurrency
- Agriculture

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Barchart Quotes API

Real-time, delayed, and end-of-day price quotes by symbol across stocks, indexes, mutual funds, ETFs, futures, forex, and cryptocurrencies — `getQuote`, `getQuoteEod`, `getClosePrice` — plus market movers via `getLeaders` and 52-week `getHighsLows`.

- **Human URL:** [https://www.barchart.com/ondemand/api/getQuote](https://www.barchart.com/ondemand/api/getQuote)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart History API

Historical time series on stocks, indexes, ETFs, futures, forex, and crypto via `getHistory` — tick, minute-bar, and end-of-day data with daily, weekly, monthly, quarterly, yearly, and nearest/continuation contract variants.

- **Human URL:** [https://www.barchart.com/ondemand/api/getHistory](https://www.barchart.com/ondemand/api/getHistory)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Reference & Equities API

Reference and instrument metadata plus bulk equities by exchange — `getEquitiesByExchange`, `getInstrumentDefinition`, `getRelatedInstruments`, `getSymbolChange`, `getUniqueIdentifier` (FIGI).

- **Human URL:** [https://www.barchart.com/ondemand/api/getEquitiesByExchange](https://www.barchart.com/ondemand/api/getEquitiesByExchange)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Futures & Options API

Futures and options market data and analytics — `getFuturesByExchange`, `getFuturesOptions`, `getFuturesOptionsEOD`, `getFuturesSpreads`, `getEquityOptions`, `getOptionsScreener`, and contract reference via `getFuturesSpecifications` and `getFuturesExpirations`.

- **Human URL:** [https://www.barchart.com/ondemand/api/getFuturesOptions](https://www.barchart.com/ondemand/api/getFuturesOptions)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Fundamentals API

Company fundamentals and financial statements — `getProfile`, `getFinancialHighlights`, `getFinancialRatios`, `getIncomeStatements`, `getBalanceSheets`, `getCashFlow`, `getRatings`, `getCompetitors`, `getIndexMembers`.

- **Human URL:** [https://www.barchart.com/ondemand/api/getProfile](https://www.barchart.com/ondemand/api/getProfile)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Corporate Actions & Earnings API

Splits, dividends, and earnings reference data — `getCorporateActions`, `getEarningsEstimates`, `getDividendData`, `getDividendStocks`, plus forward calendars via `getEarningsCalendar` and `getDividendsCalendar`.

- **Human URL:** [https://www.barchart.com/ondemand/api](https://www.barchart.com/ondemand/api)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Cryptocurrency API

Spot cryptocurrency market data — `getCrypto` for current spot prices (Bitcoin, Ethereum, Ripple, Litecoin, etc.) and `getCryptoHistory` for historical spot time series.

- **Human URL:** [https://www.barchart.com/ondemand/api](https://www.barchart.com/ondemand/api)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Commodities & Agriculture API

Physical commodity, agricultural, and economic reference data — `getGrainBids`, `getUSDAGrainPrices`, `getCmdtyStats`, `getBLSIndexes`, `getCmdtyCalendar`, `getFuelPrices`, `getCropFactors`, `getYieldForecastPlanet`, and `getForexForwardCurves`.

- **Human URL:** [https://www.barchart.com/ondemand/api](https://www.barchart.com/ondemand/api)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Technicals & Charts API

Technical analysis and charting data — `getChart`, `getTechnicals`, `getTechnicalIndicatorData`, `getSignal`, `getMomentum`, and `getSectors`.

- **Human URL:** [https://www.barchart.com/ondemand/api](https://www.barchart.com/ondemand/api)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart News & Filings API

Financial news and regulatory filings — `getNews`, `getNewsSources`, `getNewsCategories`, and `getSECFilings`.

- **Human URL:** [https://www.barchart.com/ondemand/api](https://www.barchart.com/ondemand/api)
- **Base URL:** `https://ondemand.websol.barchart.com`

### Barchart Weather API

Weather data via `getWeather` — current conditions, forecasts, and maps by zip code, complementing Barchart's agricultural and commodity data.

- **Human URL:** [https://www.barchart.com/ondemand/api/getWeather](https://www.barchart.com/ondemand/api/getWeather)
- **Base URL:** `https://ondemand.websol.barchart.com`

## Common Properties

- [Authentication](authentication/barchart-authentication.yml)
- [Domain Security](security/barchart-domain-security.yml)
- [LinkedIn](https://www.linkedin.com/company/barchart-com)
- [Website](https://www.barchart.com)
- [Documentation](https://www.barchart.com/ondemand/api)
- [Sign Up](https://www.barchart.com/solutions/services/ondemand)
- [Plans](plans/barchart-plans-pricing.yml)
- [Rate Limits](rate-limits/barchart-rate-limits.yml)
- [Fin Ops](finops/barchart-finops.yml)

## Review

Does Barchart expose a documented public WebSocket API? **No.** See [review.yml](review.yml). Barchart's documented public surface is request/response REST/SOAP with an `apikey`. Real-time push exists only as sales-gated products (the Event-Based API over REST/Socket.IO and a separate streaming market-data service), with no published raw public WebSocket contract.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
