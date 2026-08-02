
# PromptsCreateResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`created` | number
`skipped` | number
`totalAfter` | number
`promptsAvailable` | number
`data` | [Array&lt;PromptsCreateResponseDataInner&gt;](PromptsCreateResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { PromptsCreateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "created": null,
  "skipped": null,
  "totalAfter": null,
  "promptsAvailable": null,
  "data": null,
  "requestId": null,
} satisfies PromptsCreateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptsCreateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


