
# CreateWebhookRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`eventType` | string
`targetUrl` | string

## Example

```typescript
import type { CreateWebhookRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "eventType": null,
  "targetUrl": null,
} satisfies CreateWebhookRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateWebhookRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


