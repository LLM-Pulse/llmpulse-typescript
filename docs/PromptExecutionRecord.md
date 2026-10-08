
# PromptExecutionRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`promptId` | number
`executedAt` | Date
`durationMs` | number
`success` | boolean
`model` | string
`fanOutQueries` | Array&lt;string&gt;
`hasMention` | boolean
`hasCitation` | boolean
`mentionsCount` | number
`citationsCount` | number
`appUrl` | string

## Example

```typescript
import type { PromptExecutionRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "promptId": null,
  "executedAt": null,
  "durationMs": null,
  "success": null,
  "model": null,
  "fanOutQueries": null,
  "hasMention": null,
  "hasCitation": null,
  "mentionsCount": null,
  "citationsCount": null,
  "appUrl": null,
} satisfies PromptExecutionRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptExecutionRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


