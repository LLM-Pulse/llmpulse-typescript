
# AiModelInsightsReportFiltersEcho

The filters a position distribution or AI Overview report was computed with, as the server resolved them. A filter that was not given is left out, except from, to, granularity and competitors.

## Properties

Name | Type
------------ | -------------
`from` | Date
`to` | Date
`granularity` | string
`countryCode` | string
`languageCode` | string
`collectionId` | string
`promptType` | string
`brandKind` | string
`model` | string
`competitors` | Array&lt;number&gt;
`brand1` | string
`brand2` | string

## Example

```typescript
import type { AiModelInsightsReportFiltersEcho } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "from": null,
  "to": null,
  "granularity": null,
  "countryCode": null,
  "languageCode": null,
  "collectionId": null,
  "promptType": null,
  "brandKind": null,
  "model": null,
  "competitors": null,
  "brand1": null,
  "brand2": null,
} satisfies AiModelInsightsReportFiltersEcho

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelInsightsReportFiltersEcho
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


