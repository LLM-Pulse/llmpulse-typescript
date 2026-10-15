
# CustomReportSummary


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`dateRange` | [CustomReportDateRange](CustomReportDateRange.md)
`schedule` | [CustomReportSchedule](CustomReportSchedule.md)
`recipientsCount` | number
`published` | boolean
`publicLinkActive` | boolean
`passwordProtected` | boolean
`portalOnly` | boolean
`widgetCount` | number
`widgets` | [Array&lt;CustomReportWidgetRef&gt;](CustomReportWidgetRef.md)
`lastSentAt` | Date
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { CustomReportSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "dateRange": null,
  "schedule": null,
  "recipientsCount": null,
  "published": null,
  "publicLinkActive": null,
  "passwordProtected": null,
  "portalOnly": null,
  "widgetCount": null,
  "widgets": null,
  "lastSentAt": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies CustomReportSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


