
# GeoAudit


## Properties

Name | Type
------------ | -------------
`id` | string
`auditType` | string
`target` | string
`countryCode` | string
`cadence` | string
`status` | string
`pausedReason` | string
`schedule` | [GeoAuditSchedule](GeoAuditSchedule.md)
`nextRunAt` | Date
`emailAlerts` | boolean
`recurringAvailable` | boolean
`checksTracked` | boolean
`latestRun` | [GeoAuditRun](GeoAuditRun.md)
`openIssues` | number
`openCriticalIssues` | number
`createdAt` | Date
`appUrl` | string

## Example

```typescript
import type { GeoAudit } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "auditType": null,
  "target": null,
  "countryCode": null,
  "cadence": null,
  "status": null,
  "pausedReason": null,
  "schedule": null,
  "nextRunAt": null,
  "emailAlerts": null,
  "recurringAvailable": null,
  "checksTracked": null,
  "latestRun": null,
  "openIssues": null,
  "openCriticalIssues": null,
  "createdAt": null,
  "appUrl": null,
} satisfies GeoAudit

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAudit
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


