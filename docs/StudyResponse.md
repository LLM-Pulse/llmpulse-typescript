
# StudyResponse

One custom AI study with its brief, subjects, dimensions and latest reports

## Properties

Name | Type
------------ | -------------
`id` | number
`title` | string
`studyType` | string
`cadence` | string
`status` | string
`projectId` | number
`subjectsCount` | number
`aiModels` | Array&lt;string&gt;
`outputLanguageCode` | string
`createdAt` | Date
`lastReportAt` | Date
`brief` | string
`subjects` | Array&lt;string&gt;
`dimensions` | Array&lt;string&gt;
`reports` | [Array&lt;ReputationReportSummary&gt;](ReputationReportSummary.md)
`requestId` | string

## Example

```typescript
import type { StudyResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": null,
  "studyType": null,
  "cadence": null,
  "status": null,
  "projectId": null,
  "subjectsCount": null,
  "aiModels": null,
  "outputLanguageCode": null,
  "createdAt": null,
  "lastReportAt": null,
  "brief": null,
  "subjects": null,
  "dimensions": null,
  "reports": null,
  "requestId": null,
} satisfies StudyResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as StudyResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


