
# MarketHistoryChartResponse

Response envelope for GET /v1/market/history/chart (Quant only).

## Properties

Name | Type
------------ | -------------
`meta` | [MarketHistoryChartMeta](MarketHistoryChartMeta.md)
`series` | [Array&lt;MarketHistoryChartSeries&gt;](MarketHistoryChartSeries.md)

## Example

```typescript
import type { MarketHistoryChartResponse } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "meta": null,
  "series": null,
} satisfies MarketHistoryChartResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketHistoryChartResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


