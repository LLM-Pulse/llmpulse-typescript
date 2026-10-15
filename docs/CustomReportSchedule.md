
# CustomReportSchedule


## Properties

Name | Type
------------ | -------------
`enabled` | boolean
`dayOfWeek` | number
`hour` | number
`timezone` | string

## Example

```typescript
import type { CustomReportSchedule } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "enabled": null,
  "dayOfWeek": null,
  "hour": null,
  "timezone": null,
} satisfies CustomReportSchedule

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportSchedule
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


