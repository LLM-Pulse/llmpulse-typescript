
# SentimentRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`promptExecutionId` | number
`promptText` | string
`model` | string
`analysis` | string
`score` | number
`comment` | string
`topics` | string
`competitorId` | number
`competitorName` | string
`isBrandSentiment` | boolean
`executedAt` | Date
`createdAt` | Date

## Example

```typescript
import type { SentimentRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "promptExecutionId": null,
  "promptText": null,
  "model": null,
  "analysis": null,
  "score": null,
  "comment": null,
  "topics": null,
  "competitorId": null,
  "competitorName": null,
  "isBrandSentiment": null,
  "executedAt": null,
  "createdAt": null,
} satisfies SentimentRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SentimentRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


