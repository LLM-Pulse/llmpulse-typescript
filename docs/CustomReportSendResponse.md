
# CustomReportSendResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`id` | number
`status` | string
`recipientsCount` | number
`requestId` | string

## Example

```typescript
import type { CustomReportSendResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "id": null,
  "status": null,
  "recipientsCount": null,
  "requestId": null,
} satisfies CustomReportSendResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportSendResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


