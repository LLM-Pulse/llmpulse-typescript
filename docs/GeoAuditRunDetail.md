
# GeoAuditRunDetail


## Properties

Name | Type
------------ | -------------
`sequence` | number
`status` | string
`trigger` | string
`score` | number
`grade` | string
`scoreDelta` | number
`comparableToPrevious` | boolean
`newIssues` | number
`fixedIssues` | number
`regressedIssues` | number
`error` | string
`engineVersion` | string
`createdAt` | Date
`finishedAt` | Date
`appUrl` | string
`projectId` | number
`metrics` | { [key: string]: number; }
`resultData` | object
`requestId` | string

## Example

```typescript
import type { GeoAuditRunDetail } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "sequence": null,
  "status": null,
  "trigger": null,
  "score": null,
  "grade": null,
  "scoreDelta": null,
  "comparableToPrevious": null,
  "newIssues": null,
  "fixedIssues": null,
  "regressedIssues": null,
  "error": null,
  "engineVersion": null,
  "createdAt": null,
  "finishedAt": null,
  "appUrl": null,
  "projectId": null,
  "metrics": null,
  "resultData": null,
  "requestId": null,
} satisfies GeoAuditRunDetail

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditRunDetail
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


