
# ProjectDraftSuggestions

AI suggestions for a step. Only the key of the suggested step is sent, and only when status is ready

## Properties

Name | Type
------------ | -------------
`step` | string
`status` | string
`details` | [ProjectDraftSuggestionsDetails](ProjectDraftSuggestionsDetails.md)
`prompts` | Array&lt;string&gt;
`competitors` | [Array&lt;ProjectDraftSuggestionsCompetitorsInner&gt;](ProjectDraftSuggestionsCompetitorsInner.md)

## Example

```typescript
import type { ProjectDraftSuggestions } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "step": null,
  "status": null,
  "details": null,
  "prompts": null,
  "competitors": null,
} satisfies ProjectDraftSuggestions

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDraftSuggestions
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


