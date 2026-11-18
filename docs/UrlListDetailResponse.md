
# UrlListDetailResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`urlList` | [UrlList](UrlList.md)
`filters` | [UrlListFilters](UrlListFilters.md)
`summary` | [UrlListSummary](UrlListSummary.md)
`statusCounts` | [UrlListStatusCounts](UrlListStatusCounts.md)
`page` | number
`perPage` | number
`total` | number
`entries` | [Array&lt;UrlListEntry&gt;](UrlListEntry.md)
`requestId` | string

## Example

```typescript
import type { UrlListDetailResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "urlList": null,
  "filters": null,
  "summary": null,
  "statusCounts": null,
  "page": null,
  "perPage": null,
  "total": null,
  "entries": null,
  "requestId": null,
} satisfies UrlListDetailResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListDetailResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


