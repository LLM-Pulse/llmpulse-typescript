
# AiModelInsightsSummaryResponseSummary


## Properties

Name | Type
------------ | -------------
`mentionsByModel` | [AiModelInsightsSummaryResponseSummaryMentionsByModel](AiModelInsightsSummaryResponseSummaryMentionsByModel.md)
`citationsByModel` | [AiModelInsightsSummaryResponseSummaryCitationsByModel](AiModelInsightsSummaryResponseSummaryCitationsByModel.md)
`brandNetSentimentByModel` | [AiModelInsightsSummaryResponseSummaryBrandNetSentimentByModel](AiModelInsightsSummaryResponseSummaryBrandNetSentimentByModel.md)
`weightedVisibilityByModel` | [AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel](AiModelInsightsSummaryResponseSummaryWeightedVisibilityByModel.md)
`mentionsMarketShare` | [AiModelRateMatrix](AiModelRateMatrix.md)
`citationsMarketShare` | [AiModelRateMatrix](AiModelRateMatrix.md)
`sentimentMarketShare` | [AiModelInsightsSummaryResponseSummarySentimentMarketShare](AiModelInsightsSummaryResponseSummarySentimentMarketShare.md)
`weightedVisibilityMarketShare` | [AiModelInsightsSummaryResponseSummaryWeightedVisibilityMarketShare](AiModelInsightsSummaryResponseSummaryWeightedVisibilityMarketShare.md)

## Example

```typescript
import type { AiModelInsightsSummaryResponseSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "mentionsByModel": null,
  "citationsByModel": null,
  "brandNetSentimentByModel": null,
  "weightedVisibilityByModel": null,
  "mentionsMarketShare": null,
  "citationsMarketShare": null,
  "sentimentMarketShare": null,
  "weightedVisibilityMarketShare": null,
} satisfies AiModelInsightsSummaryResponseSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelInsightsSummaryResponseSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


