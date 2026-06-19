
# MarketItem

An item\'s price data from a specific provider.

## Properties

Name | Type
------------ | -------------
`provider` | string
`itemId` | number
`marketHashName` | string
`phase` | string
`lowestAsk` | number
`lowestAskDecimal` | string
`quantity` | number
`link` | string
`url` | string
`timestamp` | Date
`lastUpdated` | Date

## Example

```typescript
import type { MarketItem } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "itemId": null,
  "marketHashName": null,
  "phase": null,
  "lowestAsk": null,
  "lowestAskDecimal": null,
  "quantity": null,
  "link": null,
  "url": null,
  "timestamp": null,
  "lastUpdated": null,
} satisfies MarketItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


