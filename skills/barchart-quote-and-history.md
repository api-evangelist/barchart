---
name: Look up a quote and its price history
description: >-
  Fetch a current/delayed quote for one or more symbols, then pull the
  historical time series behind it, using the Barchart OnDemand API.
api: openapi/barchart-ondemand-official-openapi.yml
operations: [get-getQuote, get-getHistory, get-getQuoteEod]
generated: '2026-07-22'
method: generated
---

# Look up a quote and its price history

## Before you start
- Every request needs the `apikey` query parameter (subscription, enterprise, or free-trial key; see `authentication/barchart-authentication.yml`).
- Choose the response format by path suffix: `.json`, `.xml`, or `.csv` (e.g. `/getQuote.json`).
- All operations are HTTP GET and idempotent — retries are always safe (`conventions/barchart-conventions.yml`).

## Steps
1. **Get the quote** — `get-getQuote` (`GET /getQuote.json`) with `symbols` (comma-separated, e.g. `AAPL,GOOG,ZC*1`) and optionally `fields` for extra fields. The response envelope is `{status: {code, message}, results: []}`.
2. **Check `status.code`** — `200` success; `204` means no data for the symbol or your entitlement; `400` means fix parameters; `401` means the apikey is missing/invalid (`errors/barchart-problem-types.yml`).
3. **Pull history** — `get-getHistory` (`GET /getHistory.json`) with `symbol` (singular), `type` (e.g. `minutes`, `daily`), `startDate`/`endDate`, and `maxRecords`. Results default to 20 records unless `maxRecords` is raised.
4. **End-of-day variant** — use `get-getQuoteEod` (`GET /getQuoteEod.json`) when your entitlement is end-of-day rather than real-time/delayed.

## Rules
- Bound result sizes with `maxRecords` and date windows; there is no cursor pagination.
- Intraday data may be delayed up to ~20 minutes on some tiers; real-time requires exchange licensing.
- On `429`, back off exponentially and honor `Retry-After` (`rate-limits/barchart-rate-limits.yml`).
