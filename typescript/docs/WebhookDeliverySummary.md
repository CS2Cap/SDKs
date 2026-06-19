
# WebhookDeliverySummary

Summary of one webhook delivery job.

## Properties

Name | Type
------------ | -------------
`id` | string
`eventId` | string
`endpointId` | string
`endpointLabel` | string
`endpointUrl` | string
`platform` | string
`eventType` | string
`status` | string
`attemptCount` | number
`lastHttpStatus` | number
`error` | string
`nextAttemptAt` | Date
`createdAt` | Date
`completedAt` | Date

## Example

```typescript
import type { WebhookDeliverySummary } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "eventId": null,
  "endpointId": null,
  "endpointLabel": null,
  "endpointUrl": null,
  "platform": null,
  "eventType": null,
  "status": null,
  "attemptCount": null,
  "lastHttpStatus": null,
  "error": null,
  "nextAttemptAt": null,
  "createdAt": null,
  "completedAt": null,
} satisfies WebhookDeliverySummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WebhookDeliverySummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


