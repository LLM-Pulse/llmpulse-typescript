
# PromptSummaryRow


## Properties

Name | Type
------------ | -------------
`promptId` | number
`promptText` | string
`model` | string
`responses` | number
`mentions` | number
`citations` | number
`visibility` | number
`mentionRate` | number
`citationRate` | number
`avgMentionPosition` | number
`avgPosition` | number

## Example

```typescript
import type { PromptSummaryRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "promptId": null,
  "promptText": null,
  "model": null,
  "responses": null,
  "mentions": null,
  "citations": null,
  "visibility": null,
  "mentionRate": null,
  "citationRate": null,
  "avgMentionPosition": null,
  "avgPosition": null,
} satisfies PromptSummaryRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptSummaryRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


