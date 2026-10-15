
# SuggestedPromptsAcceptRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`ids` | Array&lt;number&gt;
`tagIds` | Array&lt;number&gt;
`tagNames` | Array&lt;string&gt;
`createMissing` | boolean

## Example

```typescript
import type { SuggestedPromptsAcceptRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "ids": null,
  "tagIds": null,
  "tagNames": null,
  "createMissing": null,
} satisfies SuggestedPromptsAcceptRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SuggestedPromptsAcceptRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


