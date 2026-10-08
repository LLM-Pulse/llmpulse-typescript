
# GeoAuditSchedule

Present for weekly and monthly audits. day is 0 (Sunday) to 6 for weekly audits and 1 to 28 for monthly ones; hour is in timezone.

## Properties

Name | Type
------------ | -------------
`day` | number
`hour` | number
`timezone` | string

## Example

```typescript
import type { GeoAuditSchedule } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "day": null,
  "hour": null,
  "timezone": null,
} satisfies GeoAuditSchedule

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditSchedule
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


