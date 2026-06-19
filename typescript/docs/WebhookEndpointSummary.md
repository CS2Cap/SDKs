
# WebhookEndpointSummary

Configured outbound webhook destination.

## Properties

Name | Type
------------ | -------------
`id` | string
`label` | string
`url` | string
`platform` | string
`secretLast4` | string
`isActive` | boolean
`lastSuccessAt` | Date
`lastFailureAt` | Date
`lastFailureMessage` | string
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { WebhookEndpointSummary } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "label": null,
  "url": null,
  "platform": null,
  "secretLast4": null,
  "isActive": null,
  "lastSuccessAt": null,
  "lastFailureAt": null,
  "lastFailureMessage": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies WebhookEndpointSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WebhookEndpointSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


