
# UrlListCreateResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`urlList` | [UrlListWithCounts](UrlListWithCounts.md)
`entriesAdded` | number
`invalidEntries` | [Array&lt;UrlListInvalidEntry&gt;](UrlListInvalidEntry.md)
`requestId` | string

## Example

```typescript
import type { UrlListCreateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "urlList": null,
  "entriesAdded": null,
  "invalidEntries": null,
  "requestId": null,
} satisfies UrlListCreateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListCreateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


