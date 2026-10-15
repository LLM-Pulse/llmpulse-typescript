
# SentimentTagsResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`page` | number
`perPage` | number
`total` | number
`requestId` | string
`from` | Date
`to` | Date
`brand` | [SentimentBreakdownBrand](SentimentBreakdownBrand.md)
`sort` | string
`sortDir` | string
`data` | [Array&lt;SentimentTagRow&gt;](SentimentTagRow.md)

## Example

```typescript
import type { SentimentTagsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "page": null,
  "perPage": null,
  "total": null,
  "requestId": null,
  "from": null,
  "to": null,
  "brand": null,
  "sort": null,
  "sortDir": null,
  "data": null,
} satisfies SentimentTagsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SentimentTagsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


