
# GeoAuditCreateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`target` | string
`auditTypes` | Array&lt;string&gt;
`cadence` | string

## Example

```typescript
import type { GeoAuditCreateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "target": null,
  "auditTypes": null,
  "cadence": null,
} satisfies GeoAuditCreateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditCreateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


