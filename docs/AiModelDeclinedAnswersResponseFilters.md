
# AiModelDeclinedAnswersResponseFilters

The prompt filters the counts were computed with, as the server resolved them. A filter that was not given is left out; model is always there.

## Properties

Name | Type
------------ | -------------
`model` | string
`countryCode` | string
`languageCode` | string
`collectionId` | string
`promptType` | string
`brandKind` | string

## Example

```typescript
import type { AiModelDeclinedAnswersResponseFilters } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "model": null,
  "countryCode": null,
  "languageCode": null,
  "collectionId": null,
  "promptType": null,
  "brandKind": null,
} satisfies AiModelDeclinedAnswersResponseFilters

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelDeclinedAnswersResponseFilters
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


