
# LlmsTxtTechnicalGeoReportResultData

The files and generation details once the report has completed; null before that

## Properties

Name | Type
------------ | -------------
`llmsTxtContent` | string
`llmsFullTxtContent` | string
`manuallyEditedAt` | Date
`contentVersion` | string
`originalLlmsTxtContent` | string
`originalLlmsFullTxtContent` | string
`crawlData` | object
`metadata` | object
`pagesCrawled` | number
`generationTimeMs` | number
`openaiTokensUsed` | number

## Example

```typescript
import type { LlmsTxtTechnicalGeoReportResultData } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "llmsTxtContent": null,
  "llmsFullTxtContent": null,
  "manuallyEditedAt": null,
  "contentVersion": null,
  "originalLlmsTxtContent": null,
  "originalLlmsFullTxtContent": null,
  "crawlData": null,
  "metadata": null,
  "pagesCrawled": null,
  "generationTimeMs": null,
  "openaiTokensUsed": null,
} satisfies LlmsTxtTechnicalGeoReportResultData

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as LlmsTxtTechnicalGeoReportResultData
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


