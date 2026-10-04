
# CatalogPromptSuggestionsAcceptResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`accepted` | [Array&lt;CatalogPromptSuggestionsAcceptResponseAcceptedInner&gt;](CatalogPromptSuggestionsAcceptResponseAcceptedInner.md)
`skipped` | [Array&lt;CatalogPromptSuggestionsAcceptResponseSkippedInner&gt;](CatalogPromptSuggestionsAcceptResponseSkippedInner.md)
`promptsAvailable` | number
`requestId` | string

## Example

```typescript
import type { CatalogPromptSuggestionsAcceptResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "accepted": null,
  "skipped": null,
  "promptsAvailable": null,
  "requestId": null,
} satisfies CatalogPromptSuggestionsAcceptResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CatalogPromptSuggestionsAcceptResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


