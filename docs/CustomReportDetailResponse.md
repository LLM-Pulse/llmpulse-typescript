
# CustomReportDetailResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`id` | number
`name` | string
`dateRange` | [CustomReportDateRange](CustomReportDateRange.md)
`schedule` | [CustomReportSchedule](CustomReportSchedule.md)
`recipientsCount` | number
`published` | boolean
`publicLinkActive` | boolean
`passwordProtected` | boolean
`portalOnly` | boolean
`lastSentAt` | Date
`createdAt` | Date
`updatedAt` | Date
`filters` | [CustomReportFilters](CustomReportFilters.md)
`comparePrevious` | boolean
`attachExcel` | boolean
`manualSendAvailableAt` | Date
`generatedAt` | Date
`blocks` | [Array&lt;CustomReportBlock&gt;](CustomReportBlock.md)
`widgets` | [Array&lt;CustomReportWidget&gt;](CustomReportWidget.md)
`requestId` | string

## Example

```typescript
import type { CustomReportDetailResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "id": null,
  "name": null,
  "dateRange": null,
  "schedule": null,
  "recipientsCount": null,
  "published": null,
  "publicLinkActive": null,
  "passwordProtected": null,
  "portalOnly": null,
  "lastSentAt": null,
  "createdAt": null,
  "updatedAt": null,
  "filters": null,
  "comparePrevious": null,
  "attachExcel": null,
  "manualSendAvailableAt": null,
  "generatedAt": null,
  "blocks": null,
  "widgets": null,
  "requestId": null,
} satisfies CustomReportDetailResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportDetailResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


