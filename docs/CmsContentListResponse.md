
# CmsContentListResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`site` | [CmsSite](CmsSite.md)
`type` | string
`status` | string
`page` | number
`perPage` | number
`total` | number
`totalPages` | number
`data` | [Array&lt;CmsContentSummary&gt;](CmsContentSummary.md)
`requestId` | string

## Example

```typescript
import type { CmsContentListResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "site": null,
  "type": null,
  "status": null,
  "page": null,
  "perPage": null,
  "total": null,
  "totalPages": null,
  "data": null,
  "requestId": null,
} satisfies CmsContentListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CmsContentListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


