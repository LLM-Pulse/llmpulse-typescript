
# StudySummary

One custom AI study

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

## Example

```typescript
import type { StudySummary } from '@llmpulse/sdk'

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
} satisfies StudySummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as StudySummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


