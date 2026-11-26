
# CitationIntelligenceFiltersEcho

The filters the response was computed with, as the server resolved them. A filter that was not given is left out.

## Properties

Name | Type
------------ | -------------
`model` | string
`collectionId` | string
`collectionIds` | Array&lt;number&gt;
`domains` | Array&lt;string&gt;
`prompt` | number
`brandKind` | string
`countryCode` | string
`languageCode` | string
`from` | string
`to` | string
`key` | string
`query` | string
`sourceType` | string
`sentiment` | string
`contentGap` | string

## Example

```typescript
import type { CitationIntelligenceFiltersEcho } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "model": null,
  "collectionId": null,
  "collectionIds": null,
  "domains": null,
  "prompt": null,
  "brandKind": null,
  "countryCode": null,
  "languageCode": null,
  "from": null,
  "to": null,
  "key": null,
  "query": null,
  "sourceType": null,
  "sentiment": null,
  "contentGap": null,
} satisfies CitationIntelligenceFiltersEcho

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationIntelligenceFiltersEcho
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


