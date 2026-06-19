
# PricesMeta

Metadata for prices and bids responses.

## Properties

Name | Type
------------ | -------------
`currency` | string
`filters` | [PricesFilterMeta](PricesFilterMeta.md)
`providersQueried` | Array&lt;string&gt;

## Example

```typescript
import type { PricesMeta } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "currency": null,
  "filters": null,
  "providersQueried": null,
} satisfies PricesMeta

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PricesMeta
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


