
# MarketHistoryChartPoint

One daily price point for a provider series.

## Properties

Name | Type
------------ | -------------
`t` | number
`price` | number
`qty` | number

## Example

```typescript
import type { MarketHistoryChartPoint } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "t": null,
  "price": null,
  "qty": null,
} satisfies MarketHistoryChartPoint

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketHistoryChartPoint
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


