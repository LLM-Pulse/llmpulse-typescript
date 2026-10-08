
# AnswerDetails


## Properties

Name | Type
------------ | -------------
`id` | number
`promptId` | number
`promptText` | string
`model` | string
`response` | string
`responseTruncated` | boolean
`executedAt` | Date
`durationMs` | number
`success` | boolean
`noResult` | boolean
`fanOutQueries` | Array&lt;string&gt;
`mentions` | Array&lt;object&gt;
`citations` | Array&lt;object&gt;
`competitorMentions` | Array&lt;object&gt;
`competitorCitations` | Array&lt;object&gt;
`sentiments` | Array&lt;object&gt;
`sources` | Array&lt;object&gt;
`shoppingProducts` | Array&lt;object&gt;
`brandEntities` | Array&lt;object&gt;
`localBusinesses` | Array&lt;object&gt;
`locale` | [AnswerDetailsLocale](AnswerDetailsLocale.md)
`appUrl` | string
`requestId` | string

## Example

```typescript
import type { AnswerDetails } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "promptId": null,
  "promptText": null,
  "model": null,
  "response": null,
  "responseTruncated": null,
  "executedAt": null,
  "durationMs": null,
  "success": null,
  "noResult": null,
  "fanOutQueries": null,
  "mentions": null,
  "citations": null,
  "competitorMentions": null,
  "competitorCitations": null,
  "sentiments": null,
  "sources": null,
  "shoppingProducts": null,
  "brandEntities": null,
  "localBusinesses": null,
  "locale": null,
  "appUrl": null,
  "requestId": null,
} satisfies AnswerDetails

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AnswerDetails
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


