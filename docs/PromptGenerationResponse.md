
# PromptGenerationResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`projectId` | number
`source` | string
`status` | string
`params` | [PromptGenerationResponseParams](PromptGenerationResponseParams.md)
`createdAt` | Date
`finishedAt` | Date
`suggestionsCount` | number
`suggestions` | [Array&lt;SuggestedPrompt&gt;](SuggestedPrompt.md)
`error` | [PromptGenerationResponseError](PromptGenerationResponseError.md)
`requestId` | string

## Example

```typescript
import type { PromptGenerationResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "projectId": null,
  "source": null,
  "status": null,
  "params": null,
  "createdAt": null,
  "finishedAt": null,
  "suggestionsCount": null,
  "suggestions": null,
  "error": null,
  "requestId": null,
} satisfies PromptGenerationResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptGenerationResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


