
# GeoAuditComparison


## Properties

Name | Type
------------ | -------------
`projectId` | number
`fromRun` | [GeoAuditRun](GeoAuditRun.md)
`toRun` | [GeoAuditRun](GeoAuditRun.md)
`comparable` | boolean
`scoreDelta` | number
`metricDeltas` | { [key: string]: number; }
`counts` | { [key: string]: number; }
`changes` | [Array&lt;GeoAuditComparisonChangesInner&gt;](GeoAuditComparisonChangesInner.md)
`requestId` | string

## Example

```typescript
import type { GeoAuditComparison } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "fromRun": null,
  "toRun": null,
  "comparable": null,
  "scoreDelta": null,
  "metricDeltas": null,
  "counts": null,
  "changes": null,
  "requestId": null,
} satisfies GeoAuditComparison

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditComparison
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


