
# GeoAuditIssue


## Properties

Name | Type
------------ | -------------
`id` | number
`checkKey` | string
`checkTitle` | string
`subjectKey` | string
`subject` | string
`severity` | string
`state` | string
`badge` | string
`accepted` | boolean
`acceptedAt` | Date
`regressionCount` | number
`evidence` | object
`updatedAt` | Date

## Example

```typescript
import type { GeoAuditIssue } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "checkKey": null,
  "checkTitle": null,
  "subjectKey": null,
  "subject": null,
  "severity": null,
  "state": null,
  "badge": null,
  "accepted": null,
  "acceptedAt": null,
  "regressionCount": null,
  "evidence": null,
  "updatedAt": null,
} satisfies GeoAuditIssue

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditIssue
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


