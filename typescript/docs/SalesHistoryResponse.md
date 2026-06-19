
# SalesHistoryResponse

Recent Sales response with request metadata.

## Properties

Name | Type
------------ | -------------
`meta` | [SalesMeta](SalesMeta.md)
`items` | [Array&lt;SaleRecordDetail&gt;](SaleRecordDetail.md)
`pagination` | [PaginationMeta](PaginationMeta.md)

## Example

```typescript
import type { SalesHistoryResponse } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "meta": null,
  "items": null,
  "pagination": null,
} satisfies SalesHistoryResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SalesHistoryResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


