
# ProjectDraftResponse


## Properties

Name | Type
------------ | -------------
`draft` | [ProjectDraftRecord](ProjectDraftRecord.md)
`suggestions` | [ProjectDraftSuggestions](ProjectDraftSuggestions.md)
`limits` | [ProjectDraftResponseLimits](ProjectDraftResponseLimits.md)
`requestId` | string

## Example

```typescript
import type { ProjectDraftResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "draft": null,
  "suggestions": null,
  "limits": null,
  "requestId": null,
} satisfies ProjectDraftResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDraftResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


