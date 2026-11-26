
# CitationGroupRow

A cited URL, domain or host (view). url-view rows carry url, url_sha256 and normalized_url, plus page_cache and page_mentions when page details are included; domain and host rows carry domain or host and aggregate_details.

## Properties

Name | Type
------------ | -------------
`sourceId` | number
`view` | string
`key` | string
`totalResponses` | number
`totalCitations` | number
`citationRate` | number
`citationRateDenominator` | number
`avgCitationPosition` | number
`firstSeenAt` | Date
`lastSeenAt` | Date
`models` | { [key: string]: number; }
`url` | string
`urlSha256` | string
`normalizedUrl` | string
`pageCache` | [CitationPageCache](CitationPageCache.md)
`pageMentions` | [CitationPageMentions](CitationPageMentions.md)
`domain` | string
`host` | string
`aggregateDetails` | [CitationGroupRowAggregateDetails](CitationGroupRowAggregateDetails.md)
`citationSeries` | [CitationSeries](CitationSeries.md)

## Example

```typescript
import type { CitationGroupRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "sourceId": null,
  "view": null,
  "key": null,
  "totalResponses": null,
  "totalCitations": null,
  "citationRate": null,
  "citationRateDenominator": null,
  "avgCitationPosition": null,
  "firstSeenAt": null,
  "lastSeenAt": null,
  "models": null,
  "url": null,
  "urlSha256": null,
  "normalizedUrl": null,
  "pageCache": null,
  "pageMentions": null,
  "domain": null,
  "host": null,
  "aggregateDetails": null,
  "citationSeries": null,
} satisfies CitationGroupRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationGroupRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


