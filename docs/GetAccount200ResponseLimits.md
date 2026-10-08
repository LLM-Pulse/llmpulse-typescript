
# GetAccount200ResponseLimits


## Properties

Name | Type
------------ | -------------
`prompts` | [AccountQuota](AccountQuota.md)
`projects` | [AccountQuota](AccountQuota.md)
`competitorsPerProject` | [AccountCapacity](AccountCapacity.md)
`intelligenceTasks` | [AccountQuota](AccountQuota.md)
`teamMembers` | [AccountCapacity](AccountCapacity.md)
`recurringGeoAudits` | [AccountQuota](AccountQuota.md)
`geoAuditManualRuns` | [AccountQuota](AccountQuota.md)

## Example

```typescript
import type { GetAccount200ResponseLimits } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "prompts": null,
  "projects": null,
  "competitorsPerProject": null,
  "intelligenceTasks": null,
  "teamMembers": null,
  "recurringGeoAudits": null,
  "geoAuditManualRuns": null,
} satisfies GetAccount200ResponseLimits

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetAccount200ResponseLimits
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


