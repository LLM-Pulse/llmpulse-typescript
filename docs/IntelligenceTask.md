
# IntelligenceTask


## Properties

Name | Type
------------ | -------------
`id` | number
`publicId` | string
`projectId` | number
`taskType` | string
`title` | string
`status` | string
`promptId` | number
`promptText` | string
`agenticMode` | boolean
`customTopic` | string
`userInstructions` | string
`outputLanguageCode` | string
`wordCount` | number
`resultData` | object
`errorMessage` | string
`estimatedTime` | string
`createdAt` | Date
`processedAt` | Date
`manuallyEditedAt` | Date
`editedByUserId` | number
`requestId` | string

## Example

```typescript
import type { IntelligenceTask } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "publicId": null,
  "projectId": null,
  "taskType": null,
  "title": null,
  "status": null,
  "promptId": null,
  "promptText": null,
  "agenticMode": null,
  "customTopic": null,
  "userInstructions": null,
  "outputLanguageCode": null,
  "wordCount": null,
  "resultData": null,
  "errorMessage": null,
  "estimatedTime": null,
  "createdAt": null,
  "processedAt": null,
  "manuallyEditedAt": null,
  "editedByUserId": null,
  "requestId": null,
} satisfies IntelligenceTask

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IntelligenceTask
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


