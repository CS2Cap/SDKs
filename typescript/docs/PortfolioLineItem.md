
# PortfolioLineItem

Valuation line item for one portfolio entry.

## Properties

Name | Type
------------ | -------------
`itemId` | number
`marketHashName` | string
`phase` | string
`quantity` | number
`bestAsk` | number
`bestBid` | number
`itemValue` | number
`imageUrl` | string
`rarityName` | string
`rarityColor` | string
`providers` | [Array&lt;BatchPriceQuote&gt;](BatchPriceQuote.md)

## Example

```typescript
import type { PortfolioLineItem } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "itemId": null,
  "marketHashName": null,
  "phase": null,
  "quantity": null,
  "bestAsk": null,
  "bestBid": null,
  "itemValue": null,
  "imageUrl": null,
  "rarityName": null,
  "rarityColor": null,
  "providers": null,
} satisfies PortfolioLineItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PortfolioLineItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


