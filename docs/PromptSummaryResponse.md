
# PromptSummaryResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`filters` | object
`breakdown` | string
`sort` | string
`sortDir` | string
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;PromptSummaryRow&gt;](PromptSummaryRow.md)
`requestId` | string

## Example

```typescript
import type { PromptSummaryResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "filters": null,
  "breakdown": null,
  "sort": null,
  "sortDir": null,
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
  "requestId": null,
} satisfies PromptSummaryResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptSummaryResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


