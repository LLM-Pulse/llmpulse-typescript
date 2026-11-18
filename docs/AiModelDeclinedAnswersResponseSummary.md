
# AiModelDeclinedAnswersResponseSummary


## Properties

Name | Type
------------ | -------------
`answers` | number
`declined` | number
`declineRate` | number
`safetyFilter` | number
`safetyFilterRate` | number
`topicRefusal` | number
`topicRefusalRate` | number
`lastDeclinedAt` | Date

## Example

```typescript
import type { AiModelDeclinedAnswersResponseSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "answers": null,
  "declined": null,
  "declineRate": null,
  "safetyFilter": null,
  "safetyFilterRate": null,
  "topicRefusal": null,
  "topicRefusalRate": null,
  "lastDeclinedAt": null,
} satisfies AiModelDeclinedAnswersResponseSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelDeclinedAnswersResponseSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


