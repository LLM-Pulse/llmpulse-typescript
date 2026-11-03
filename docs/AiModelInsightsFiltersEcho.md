
# AiModelInsightsFiltersEcho

The filters the summary was computed with, as the server resolved them. A filter that was not given is left out, except granularity and competitors.

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
`competitors` | Array&lt;number&gt;

## Example

```typescript
import type { AiModelInsightsFiltersEcho } from '@llmpulse/sdk'

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
  "competitors": null,
} satisfies AiModelInsightsFiltersEcho

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelInsightsFiltersEcho
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


