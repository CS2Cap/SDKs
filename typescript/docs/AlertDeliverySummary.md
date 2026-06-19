
# AlertDeliverySummary

Outbound delivery result for one alert event.

## Properties

Name | Type
------------ | -------------
`channel` | string
`status` | string
`deliveryId` | string
`endpointId` | string
`endpointLabel` | string
`platform` | string
`attemptCount` | number
`lastHttpStatus` | number
`nextAttemptAt` | Date
`error` | string
`createdAt` | Date

## Example

```typescript
import type { AlertDeliverySummary } from 'cs2cap'

// TODO: Update the object below with actual values
const example = {
  "channel": null,
  "status": null,
  "deliveryId": null,
  "endpointId": null,
  "endpointLabel": null,
  "platform": null,
  "attemptCount": null,
  "lastHttpStatus": null,
  "nextAttemptAt": null,
  "error": null,
  "createdAt": null,
} satisfies AlertDeliverySummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AlertDeliverySummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


