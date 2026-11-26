
# AiOverviewResultsResponse

How often Google AI Overviews returned a result for the project\'s prompts. A result rate is a percentage (0-100) of the AI Overview runs, 0 when there is none.

## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`filters` | [AiModelInsightsReportFiltersEcho](AiModelInsightsReportFiltersEcho.md)
`granularity` | string
`summary` | [AiOverviewResultCounts](AiOverviewResultCounts.md)
`chart` | [Array&lt;AiOverviewResultsResponseChartInner&gt;](AiOverviewResultsResponseChartInner.md)
`byPrompt` | [AiOverviewResultsResponseByPrompt](AiOverviewResultsResponseByPrompt.md)
`requestId` | string

## Example

```typescript
import type { AiOverviewResultsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "filters": null,
  "granularity": null,
  "summary": null,
  "chart": null,
  "byPrompt": null,
  "requestId": null,
} satisfies AiOverviewResultsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiOverviewResultsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


