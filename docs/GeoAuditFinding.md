
# GeoAuditFinding


## Properties

Name | Type
------------ | -------------
`checkKey` | string
`checkTitle` | string
`subjectKey` | string
`subject` | string
`status` | string
`severity` | string
`evidence` | object

## Example

```typescript
import type { GeoAuditFinding } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "checkKey": null,
  "checkTitle": null,
  "subjectKey": null,
  "subject": null,
  "status": null,
  "severity": null,
  "evidence": null,
} satisfies GeoAuditFinding

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditFinding
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


