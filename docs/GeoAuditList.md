
# GeoAuditList


## Properties

Name | Type
------------ | -------------
`projectId` | number
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;GeoAudit&gt;](GeoAudit.md)
`requestId` | string

## Example

```typescript
import type { GeoAuditList } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
  "requestId": null,
} satisfies GeoAuditList

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditList
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


