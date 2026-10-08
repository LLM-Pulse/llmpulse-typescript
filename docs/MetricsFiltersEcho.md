
# MetricsFiltersEcho

The filters the response was computed with, as the server resolved them. Each endpoint echoes only the keys it reads; a filter that was not given comes back null (or an empty list).

## Properties

Name | Type
------------ | -------------
`metrics` | Array&lt;string&gt;
`granularity` | string
`model` | string
`collectionId` | string
`collectionIds` | Array&lt;number&gt;
`domains` | Array&lt;string&gt;
`countryCode` | string
`languageCode` | string
`prompt` | number
`promptType` | string
`brandKind` | string
`competitors` | Array&lt;number&gt;
`includeProject` | boolean
`query` | string

## Example

```typescript
import type { MetricsFiltersEcho } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "metrics": null,
  "granularity": null,
  "model": null,
  "collectionId": null,
  "collectionIds": null,
  "domains": null,
  "countryCode": null,
  "languageCode": null,
  "prompt": null,
  "promptType": null,
  "brandKind": null,
  "competitors": null,
  "includeProject": null,
  "query": null,
} satisfies MetricsFiltersEcho

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MetricsFiltersEcho
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


