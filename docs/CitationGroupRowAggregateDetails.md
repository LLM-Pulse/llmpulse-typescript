
# CitationGroupRowAggregateDetails

domain and host views only. The distinct cited pages of the group.

## Properties

Name | Type
------------ | -------------
`uniqueUrlsCount` | number
`crawledUrlsCount` | number
`brandMentionedUrlsCount` | number
`competitorMentionedUrlsCount` | number
`lastCrawledAt` | Date

## Example

```typescript
import type { CitationGroupRowAggregateDetails } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "uniqueUrlsCount": null,
  "crawledUrlsCount": null,
  "brandMentionedUrlsCount": null,
  "competitorMentionedUrlsCount": null,
  "lastCrawledAt": null,
} satisfies CitationGroupRowAggregateDetails

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationGroupRowAggregateDetails
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


