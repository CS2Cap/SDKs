
# BatchBidQuote

Bid quote from a single provider for one item.

## Properties

Name | Type
------------ | -------------
`provider` | string
`highestBid` | number
`highestBidDecimal` | string
`numBids` | number
`timestamp` | Date
`lastUpdated` | Date

## Example

```typescript
import type { BatchBidQuote } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "highestBid": null,
  "highestBidDecimal": null,
  "numBids": null,
  "timestamp": null,
  "lastUpdated": null,
} satisfies BatchBidQuote

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchBidQuote
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


