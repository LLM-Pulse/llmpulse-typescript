
# PromptGenerationRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`source` | string
`query` | string
`count` | number
`countryCode` | string
`languageCode` | string
`competitorId` | number
`searchType` | string
`keywords` | Array&lt;string&gt;
`sourceCountryCode` | string
`sourceLanguageCode` | string
`minWords` | number
`allCountries` | boolean
`property` | string

## Example

```typescript
import type { PromptGenerationRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "source": null,
  "query": null,
  "count": null,
  "countryCode": null,
  "languageCode": null,
  "competitorId": null,
  "searchType": null,
  "keywords": null,
  "sourceCountryCode": null,
  "sourceLanguageCode": null,
  "minWords": null,
  "allCountries": null,
  "property": null,
} satisfies PromptGenerationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptGenerationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


