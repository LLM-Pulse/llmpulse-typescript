
# UrlListEntriesAddRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`entries` | [Array&lt;UrlListEntryInput&gt;](UrlListEntryInput.md)
`matchType` | string

## Example

```typescript
import type { UrlListEntriesAddRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "entries": null,
  "matchType": null,
} satisfies UrlListEntriesAddRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListEntriesAddRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


