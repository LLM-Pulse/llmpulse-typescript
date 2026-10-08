
# IntelligenceTaskSummary


## Properties

Name | Type
------------ | -------------
`id` | number
`publicId` | string
`taskType` | string
`title` | string
`status` | string
`promptId` | number
`promptText` | string
`wordCount` | number
`manuallyEditedAt` | Date
`createdAt` | Date
`processedAt` | Date

## Example

```typescript
import type { IntelligenceTaskSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "publicId": null,
  "taskType": null,
  "title": null,
  "status": null,
  "promptId": null,
  "promptText": null,
  "wordCount": null,
  "manuallyEditedAt": null,
  "createdAt": null,
  "processedAt": null,
} satisfies IntelligenceTaskSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IntelligenceTaskSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


