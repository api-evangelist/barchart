---
name: Build a company fundamentals snapshot
description: >-
  Assemble a company profile with financial highlights, statements, and
  analyst ratings for an equity symbol using the Barchart OnDemand API.
api: openapi/barchart-ondemand-official-openapi.yml
operations: [get-getProfile, get-getFinancialHighlights, get-getIncomeStatements, get-getBalanceSheets, get-getRatings, get-getCorporateActions]
generated: '2026-07-22'
method: generated
---

# Build a company fundamentals snapshot

## Before you start
- Every request needs the `apikey` query parameter; fundamentals access depends on your subscription entitlement.
- All operations are GET with the `{status, results}` envelope; `204` means the symbol has no data in your entitlement.

## Steps
1. **Profile** — `get-getProfile` (`GET /getProfile.json`) with `symbols`; add `fields` for extended descriptors.
2. **Highlights and ratios** — `get-getFinancialHighlights` (`GET /getFinancialHighlights.json`) with `symbols` for key metrics.
3. **Statements** — `get-getIncomeStatements` (`GET /getIncomeStatements.json`) and `get-getBalanceSheets` (`GET /getBalanceSheets.json`) with `symbols` and `frequency`-style params as documented per operation.
4. **Analyst ratings** — `get-getRatings` (`GET /getRatings.json`) with `symbols`.
5. **Corporate actions** — `get-getCorporateActions` (`GET /getCorporateActions.json`) with `symbols` and a `startDate` window for splits/dividends context.

## Rules
- Batch symbols where the operation accepts a comma-separated `symbols` list to conserve request quota.
- Raise `maxRecords` on statement/action lists — the default cap is 20 records.
- Retries are safe (read-only surface); on `401` re-check the apikey entitlement rather than retrying.
