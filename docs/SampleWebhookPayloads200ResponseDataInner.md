
# SampleWebhookPayloads200ResponseDataInner


## Properties

Name | Type
------------ | -------------
`event` | string
`occurredAt` | Date
`projectId` | number
`subscriptionId` | number
`data` | object

## Example

```typescript
import type { SampleWebhookPayloads200ResponseDataInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "event": null,
  "occurredAt": null,
  "projectId": null,
  "subscriptionId": null,
  "data": null,
} satisfies SampleWebhookPayloads200ResponseDataInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SampleWebhookPayloads200ResponseDataInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


