
# RemovePromptTagsRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`promptIds` | Array&lt;number&gt;
`tagIds` | Array&lt;number&gt;
`tagNames` | Array&lt;string&gt;

## Example

```typescript
import type { RemovePromptTagsRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "promptIds": null,
  "tagIds": null,
  "tagNames": null,
} satisfies RemovePromptTagsRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RemovePromptTagsRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


