
# BatchPriceQuote

Price quote from a single provider for one item.

## Properties

Name | Type
------------ | -------------
`provider` | string
`lowestAsk` | number
`lowestAskDecimal` | string
`quantity` | number
`timestamp` | Date
`lastUpdated` | Date

## Example

```typescript
import type { BatchPriceQuote } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "lowestAsk": null,
  "lowestAskDecimal": null,
  "quantity": null,
  "timestamp": null,
  "lastUpdated": null,
} satisfies BatchPriceQuote

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchPriceQuote
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


