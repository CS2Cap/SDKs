
# MarketItemAnalyticsSummary

Quick summary for single-item analytics.

## Properties

Name | Type
------------ | -------------
`providerCount` | number
`bestAskUsd` | string
`bestBidUsd` | string
`avgSpreadPct` | number
`totalVolume24h` | number
`liquidity` | number
`supply` | number
`rank` | number
`marketcap` | string
`priceRate24h` | number
`priceDiff24h` | string
`priceRate7d` | number
`priceDiff7d` | string
`priceRate30d` | number
`priceDiff30d` | string
`sales1d` | number
`sales7d` | number
`sales30d` | number
`steamSales7d` | number
`steamSales30d` | number
`listingScore` | number
`gapScore` | number
`volumeScore` | number
`stabilityScore` | number
`externalScore` | number
`liquidityLastUpdated` | Date

## Example

```typescript
import type { MarketItemAnalyticsSummary } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "providerCount": null,
  "bestAskUsd": null,
  "bestBidUsd": null,
  "avgSpreadPct": null,
  "totalVolume24h": null,
  "liquidity": null,
  "supply": null,
  "rank": null,
  "marketcap": null,
  "priceRate24h": null,
  "priceDiff24h": null,
  "priceRate7d": null,
  "priceDiff7d": null,
  "priceRate30d": null,
  "priceDiff30d": null,
  "sales1d": null,
  "sales7d": null,
  "sales30d": null,
  "steamSales7d": null,
  "steamSales30d": null,
  "listingScore": null,
  "gapScore": null,
  "volumeScore": null,
  "stabilityScore": null,
  "externalScore": null,
  "liquidityLastUpdated": null,
} satisfies MarketItemAnalyticsSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketItemAnalyticsSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


