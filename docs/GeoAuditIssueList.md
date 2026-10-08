
# GeoAuditIssueList


## Properties

Name | Type
------------ | -------------
`projectId` | number
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;GeoAuditIssue&gt;](GeoAuditIssue.md)
`requestId` | string

## Example

```typescript
import type { GeoAuditIssueList } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
  "requestId": null,
} satisfies GeoAuditIssueList

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditIssueList
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


