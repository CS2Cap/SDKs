
# MarketHistoryChartMeta

Metadata for /v1/market/history/chart.

## Properties

Name | Type
------------ | -------------
`itemId` | number
`marketHashName` | string
`currency` | string
`start` | Date
`end` | Date
`providers` | Array&lt;string&gt;

## Example

```typescript
import type { MarketHistoryChartMeta } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "itemId": null,
  "marketHashName": null,
  "currency": null,
  "start": null,
  "end": null,
  "providers": null,
} satisfies MarketHistoryChartMeta

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketHistoryChartMeta
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


