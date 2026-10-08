
# GeoAuditUpdateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`cadence` | string
`scheduleDay` | number
`scheduleHour` | number
`status` | string
`emailAlerts` | boolean

## Example

```typescript
import type { GeoAuditUpdateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "cadence": null,
  "scheduleDay": null,
  "scheduleHour": null,
  "status": null,
  "emailAlerts": null,
} satisfies GeoAuditUpdateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAuditUpdateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


