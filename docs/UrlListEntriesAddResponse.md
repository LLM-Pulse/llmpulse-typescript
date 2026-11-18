
# UrlListEntriesAddResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`urlListId` | number
`added` | number
`updated` | number
`invalidEntries` | [Array&lt;UrlListInvalidEntry&gt;](UrlListInvalidEntry.md)
`entriesCount` | number
`requestId` | string

## Example

```typescript
import type { UrlListEntriesAddResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "urlListId": null,
  "added": null,
  "updated": null,
  "invalidEntries": null,
  "entriesCount": null,
  "requestId": null,
} satisfies UrlListEntriesAddResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListEntriesAddResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


