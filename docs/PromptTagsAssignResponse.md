
# PromptTagsAssignResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`promptsTargeted` | number
`tagsAttached` | [Array&lt;TagRef&gt;](TagRef.md)
`newLinksCreated` | number
`skippedAlreadyLinked` | number
`missingTagNames` | Array&lt;string&gt;
`ignoredPromptIds` | Array&lt;number&gt;
`requestId` | string

## Example

```typescript
import type { PromptTagsAssignResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "promptsTargeted": null,
  "tagsAttached": null,
  "newLinksCreated": null,
  "skippedAlreadyLinked": null,
  "missingTagNames": null,
  "ignoredPromptIds": null,
  "requestId": null,
} satisfies PromptTagsAssignResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptTagsAssignResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


