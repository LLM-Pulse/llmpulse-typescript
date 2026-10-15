
# SentimentTagRow


## Properties

Name | Type
------------ | -------------
`mentions` | number
`positive` | number
`neutral` | number
`negative` | number
`positivePct` | number
`neutralPct` | number
`negativePct` | number
`netScore` | number
`tagId` | number
`tag` | string

## Example

```typescript
import type { SentimentTagRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "mentions": null,
  "positive": null,
  "neutral": null,
  "negative": null,
  "positivePct": null,
  "neutralPct": null,
  "negativePct": null,
  "netScore": null,
  "tagId": null,
  "tag": null,
} satisfies SentimentTagRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SentimentTagRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


