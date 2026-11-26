
# AiOverviewResultsResponseByPromptDataInner


## Properties

Name | Type
------------ | -------------
`promptId` | number
`promptText` | string
`totalResponses` | number
`responsesWithResults` | number
`resultRate` | number

## Example

```typescript
import type { AiOverviewResultsResponseByPromptDataInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "promptId": null,
  "promptText": null,
  "totalResponses": null,
  "responsesWithResults": null,
  "resultRate": null,
} satisfies AiOverviewResultsResponseByPromptDataInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiOverviewResultsResponseByPromptDataInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


