
# GeoAuditComparisonChangesInner


## Properties

Name | Type
------------ | -------------
`checkKey` | string
`checkTitle` | string
`subjectKey` | string
`subject` | string
`severity` | string
`fromStatus` | string
`toStatus` | string
`change` | string

## Example

```typescript
import type { GeoAuditComparisonChangesInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "checkKey": null,
  "checkTitle": null,
  "subjectKey": null,
  "subject": null,
  "severity": null,
  "fromStatus": null,
  "toStatus": null,
  "change": null,
} satisfies GeoAuditComparisonChangesInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditComparisonChangesInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


