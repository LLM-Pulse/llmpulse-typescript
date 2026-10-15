
# PromptGenerationResponseParams

The validated request the run uses, with the project\'s locale filled in

## Properties

Name | Type
------------ | -------------
`countryCode` | string
`languageCode` | string
`query` | string
`count` | number
`competitorId` | number
`searchType` | string
`keywords` | Array&lt;string&gt;
`sourceCountryCode` | string
`sourceLanguageCode` | string
`minWords` | number
`allCountries` | boolean

## Example

```typescript
import type { PromptGenerationResponseParams } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "countryCode": null,
  "languageCode": null,
  "query": null,
  "count": null,
  "competitorId": null,
  "searchType": null,
  "keywords": null,
  "sourceCountryCode": null,
  "sourceLanguageCode": null,
  "minWords": null,
  "allCountries": null,
} satisfies PromptGenerationResponseParams

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptGenerationResponseParams
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


