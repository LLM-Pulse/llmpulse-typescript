
# AnswerRecord

One answer. Without query a row carries response and response_truncated; with query it carries snippet and match_count instead

## Properties

Name | Type
------------ | -------------
`id` | number
`promptId` | number
`promptText` | string
`model` | string
`executedAt` | Date
`durationMs` | number
`noResult` | boolean
`noResultReason` | string
`mentionsCount` | number
`citationsCount` | number
`appUrl` | string
`response` | string
`responseTruncated` | boolean
`snippet` | string
`matchCount` | number

## Example

```typescript
import type { AnswerRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "promptId": null,
  "promptText": null,
  "model": null,
  "executedAt": null,
  "durationMs": null,
  "noResult": null,
  "noResultReason": null,
  "mentionsCount": null,
  "citationsCount": null,
  "appUrl": null,
  "response": null,
  "responseTruncated": null,
  "snippet": null,
  "matchCount": null,
} satisfies AnswerRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AnswerRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


