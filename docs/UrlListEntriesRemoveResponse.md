
# UrlListEntriesRemoveResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`urlListId` | number
`removed` | number
`entriesCount` | number
`requestId` | string

## Example

```typescript
import type { UrlListEntriesRemoveResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "urlListId": null,
  "removed": null,
  "entriesCount": null,
  "requestId": null,
} satisfies UrlListEntriesRemoveResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListEntriesRemoveResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


