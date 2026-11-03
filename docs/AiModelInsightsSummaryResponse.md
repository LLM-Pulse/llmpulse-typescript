
# AiModelInsightsSummaryResponse

One entry per AI model the account has enabled or that answered in the window, in the in-app column order: the models list, which every per-model list and map in summary follows. A share, net sentiment or market share value with nothing behind it is null, because 0 is a real value; counts, totals and weighted visibility scores stay 0.

## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`filters` | [AiModelInsightsFiltersEcho](AiModelInsightsFiltersEcho.md)
`models` | [Array&lt;AiModelInsightsModel&gt;](AiModelInsightsModel.md)
`summary` | [AiModelInsightsSummaryResponseSummary](AiModelInsightsSummaryResponseSummary.md)
`requestId` | string

## Example

```typescript
import type { AiModelInsightsSummaryResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "filters": null,
  "models": null,
  "summary": null,
  "requestId": null,
} satisfies AiModelInsightsSummaryResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelInsightsSummaryResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


