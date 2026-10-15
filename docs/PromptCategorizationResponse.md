
# PromptCategorizationResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`prompt` | [PromptCategorization](PromptCategorization.md)
`requestId` | string

## Example

```typescript
import type { PromptCategorizationResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "prompt": null,
  "requestId": null,
} satisfies PromptCategorizationResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptCategorizationResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


