
# AiModelDeclinedAnswersResponse

How often one AI model declined to answer the project\'s prompts. An answer is a finished run of the model, a declined one included; a declined answer counts as no answer and never enters the metrics. The window starts at the tracking period holding its first day, and summary, chart and by_prompt count that same window.

## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`model` | string
`cadence` | string
`filters` | [AiModelDeclinedAnswersResponseFilters](AiModelDeclinedAnswersResponseFilters.md)
`summary` | [AiModelDeclinedAnswersResponseSummary](AiModelDeclinedAnswersResponseSummary.md)
`chart` | [Array&lt;AiModelDeclinedAnswersResponseChartInner&gt;](AiModelDeclinedAnswersResponseChartInner.md)
`byPrompt` | [AiModelDeclinedAnswersResponseByPrompt](AiModelDeclinedAnswersResponseByPrompt.md)
`requestId` | string

## Example

```typescript
import type { AiModelDeclinedAnswersResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "model": null,
  "cadence": null,
  "filters": null,
  "summary": null,
  "chart": null,
  "byPrompt": null,
  "requestId": null,
} satisfies AiModelDeclinedAnswersResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelDeclinedAnswersResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


