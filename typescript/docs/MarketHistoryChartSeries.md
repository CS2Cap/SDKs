
# MarketHistoryChartSeries

Per-provider daily price-point series.

## Properties

Name | Type
------------ | -------------
`provider` | string
`data` | [Array&lt;MarketHistoryChartPoint&gt;](MarketHistoryChartPoint.md)

## Example

```typescript
import type { MarketHistoryChartSeries } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "data": null,
} satisfies MarketHistoryChartSeries

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketHistoryChartSeries
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


