
# CitedUrlOccurrencesResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`page` | number
`perPage` | number
`total` | number
`requestId` | string
`urlSha256` | string
`data` | [Array&lt;CitedUrlOccurrencesResponseAllOfData&gt;](CitedUrlOccurrencesResponseAllOfData.md)

## Example

```typescript
import type { CitedUrlOccurrencesResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "page": null,
  "perPage": null,
  "total": null,
  "requestId": null,
  "urlSha256": null,
  "data": null,
} satisfies CitedUrlOccurrencesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitedUrlOccurrencesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


