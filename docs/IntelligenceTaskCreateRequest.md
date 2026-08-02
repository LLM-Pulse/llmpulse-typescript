
# IntelligenceTaskCreateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`taskType` | string
`promptId` | number
`customTopic` | string
`userInstructions` | string
`outputLanguageCode` | string
`existingContent` | string
`existingContentUrl` | string

## Example

```typescript
import type { IntelligenceTaskCreateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "taskType": null,
  "promptId": null,
  "customTopic": null,
  "userInstructions": null,
  "outputLanguageCode": null,
  "existingContent": null,
  "existingContentUrl": null,
} satisfies IntelligenceTaskCreateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IntelligenceTaskCreateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


