
# OwnedMediaCitingPromptsResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`provider` | string
`from` | Date
`to` | Date
`item` | [OwnedMediaCitedItem](OwnedMediaCitedItem.md)
`citationCount` | number
`promptCount` | number
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;OwnedMediaCitingAnswer&gt;](OwnedMediaCitingAnswer.md)
`requestId` | string

## Example

```typescript
import type { OwnedMediaCitingPromptsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "provider": null,
  "from": null,
  "to": null,
  "item": null,
  "citationCount": null,
  "promptCount": null,
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
  "requestId": null,
} satisfies OwnedMediaCitingPromptsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaCitingPromptsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


