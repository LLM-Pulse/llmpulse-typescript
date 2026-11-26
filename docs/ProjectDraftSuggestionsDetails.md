
# ProjectDraftSuggestionsDetails


## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`industry` | Array&lt;string&gt;
`matchingNames` | Array&lt;string&gt;

## Example

```typescript
import type { ProjectDraftSuggestionsDetails } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "description": null,
  "industry": null,
  "matchingNames": null,
} satisfies ProjectDraftSuggestionsDetails

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDraftSuggestionsDetails
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


