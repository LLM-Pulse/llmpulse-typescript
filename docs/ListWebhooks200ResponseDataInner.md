
# ListWebhooks200ResponseDataInner


## Properties

Name | Type
------------ | -------------
`id` | number
`projectId` | number
`eventType` | string
`targetUrl` | string
`disabled` | boolean
`failureCount` | number
`lastDeliveredAt` | Date
`createdAt` | Date

## Example

```typescript
import type { ListWebhooks200ResponseDataInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "projectId": null,
  "eventType": null,
  "targetUrl": null,
  "disabled": null,
  "failureCount": null,
  "lastDeliveredAt": null,
  "createdAt": null,
} satisfies ListWebhooks200ResponseDataInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListWebhooks200ResponseDataInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


