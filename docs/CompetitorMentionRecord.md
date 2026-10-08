
# CompetitorMentionRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`competitorId` | number
`name` | string
`domain` | string
`promptExecutionId` | number
`createdAt` | Date

## Example

```typescript
import type { CompetitorMentionRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "competitorId": null,
  "name": null,
  "domain": null,
  "promptExecutionId": null,
  "createdAt": null,
} satisfies CompetitorMentionRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CompetitorMentionRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


