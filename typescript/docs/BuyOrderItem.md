
# BuyOrderItem

Buy order data for a specific item from a provider.

## Properties

Name | Type
------------ | -------------
`itemId` | number
`marketHashName` | string
`phase` | string
`provider` | string
`highestBid` | number
`highestBidDecimal` | string
`numBids` | number
`timestamp` | Date
`lastUpdated` | Date

## Example

```typescript
import type { BuyOrderItem } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "itemId": null,
  "marketHashName": null,
  "phase": null,
  "provider": null,
  "highestBid": null,
  "highestBidDecimal": null,
  "numBids": null,
  "timestamp": null,
  "lastUpdated": null,
} satisfies BuyOrderItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BuyOrderItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


