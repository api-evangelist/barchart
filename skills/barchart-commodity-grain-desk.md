---
name: Run a commodity grain desk lookup
description: >-
  Pull local grain bids, USDA prices, commodity statistics, and agricultural
  weather for a region using the Barchart OnDemand API.
api: openapi/barchart-ondemand-official-openapi.yml
operations: [get-getGrainBids, get-getUSDAGrainPrices, get-getCmdtyStats, get-getGrainInstruments, get-getWeather]
generated: '2026-07-22'
method: generated
---

# Run a commodity grain desk lookup

## Before you start
- Every request needs the `apikey` query parameter; agricultural datasets are entitlement-scoped.
- Responses use the `{status, results}` envelope; formats `.json`, `.xml`, `.csv` by path suffix.

## Steps
1. **Grain instruments** — `get-getGrainInstruments` (`GET /getGrainInstruments.json`) to resolve the commodities and root symbols available to your key.
2. **Local bids** — `get-getGrainBids` (`GET /getGrainBids.json`) with location parameters as documented (e.g. zip/location and commodity filters) to get cash bids from local elevators.
3. **USDA prices** — `get-getUSDAGrainPrices` (`GET /getUSDAGrainPrices.json`) for government-reported grain prices.
4. **Commodity statistics** — `get-getCmdtyStats` (`GET /getCmdtyStats.json`) for supply/demand and statistical series; use `get-getCmdtyStatsId` to fetch a specific series by id.
5. **Weather** — `get-getWeather` (`GET /getWeather.json`) for current conditions and forecasts relevant to the growing region.

## Rules
- Some agricultural datasets refresh on schedules, not continuously — cache accordingly.
- Bound lists with `maxRecords` (default cap 20) and date windows.
- All operations are GET and safe to retry; on `204` the location/commodity has no data in your entitlement.
