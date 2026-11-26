
# CitationPageMentionsMentionsInner


## Properties

Name | Type
------------ | -------------
`id` | number
`matchedKey` | string
`snippet` | string
`startOffset` | number
`endOffset` | number
`position` | number
`actorType` | string
`competitorId` | number
`actorName` | string
`actorDomain` | string

## Example

```typescript
import type { CitationPageMentionsMentionsInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "matchedKey": null,
  "snippet": null,
  "startOffset": null,
  "endOffset": null,
  "position": null,
  "actorType": null,
  "competitorId": null,
  "actorName": null,
  "actorDomain": null,
} satisfies CitationPageMentionsMentionsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationPageMentionsMentionsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


