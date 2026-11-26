
# CitationPageMentions

The brands the cited page mentions, from its analysis for the requesting project. A page not yet analyzed for it has null brand_mentioned, competitor_mentioned and brand_position and empty lists.

## Properties

Name | Type
------------ | -------------
`brandMentioned` | boolean
`competitorMentioned` | boolean
`brandPosition` | number
`contentGapStatus` | string
`brands` | [Array&lt;CitationPageMentionsBrandsInner&gt;](CitationPageMentionsBrandsInner.md)
`mentions` | [Array&lt;CitationPageMentionsMentionsInner&gt;](CitationPageMentionsMentionsInner.md)

## Example

```typescript
import type { CitationPageMentions } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "brandMentioned": null,
  "competitorMentioned": null,
  "brandPosition": null,
  "contentGapStatus": null,
  "brands": null,
  "mentions": null,
} satisfies CitationPageMentions

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationPageMentions
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


