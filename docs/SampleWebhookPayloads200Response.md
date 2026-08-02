
# SampleWebhookPayloads200Response


## Properties

Name | Type
------------ | -------------
`eventType` | string
`data` | [Array&lt;SampleWebhookPayloads200ResponseDataInner&gt;](SampleWebhookPayloads200ResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { SampleWebhookPayloads200Response } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "eventType": null,
  "data": null,
  "requestId": null,
} satisfies SampleWebhookPayloads200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SampleWebhookPayloads200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


