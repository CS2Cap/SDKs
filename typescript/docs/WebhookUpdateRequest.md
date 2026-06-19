
# WebhookUpdateRequest

Update mutable outbound webhook destination fields.

## Properties

Name | Type
------------ | -------------
`label` | string
`url` | string
`platform` | string
`isActive` | boolean

## Example

```typescript
import type { WebhookUpdateRequest } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "label": null,
  "url": null,
  "platform": null,
  "isActive": null,
} satisfies WebhookUpdateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WebhookUpdateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


