
# PromptsResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`page` | number
`perPage` | number
`total` | number
`requestId` | string
`data` | [Array&lt;PromptRecord&gt;](PromptRecord.md)

## Example

```typescript
import type { PromptsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "page": null,
  "perPage": null,
  "total": null,
  "requestId": null,
  "data": null,
} satisfies PromptsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


