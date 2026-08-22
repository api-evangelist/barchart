# Barchart (barchart)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
