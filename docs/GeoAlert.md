
# GeoAlert


## Properties

Name | Type
------------ | -------------
`id` | number
`auditId` | string
`auditType` | string
`target` | string
`runSequence` | number
`severity` | string
`events` | [Array&lt;GeoAlertEventsInner&gt;](GeoAlertEventsInner.md)
`createdAt` | Date
`appUrl` | string

## Example

```typescript
import type { GeoAlert } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "auditId": null,
  "auditType": null,
  "target": null,
  "runSequence": null,
  "severity": null,
  "events": null,
  "createdAt": null,
  "appUrl": null,
} satisfies GeoAlert

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAlert
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


