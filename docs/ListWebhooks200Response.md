
# ListWebhooks200Response


## Properties

Name | Type
------------ | -------------
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;ListWebhooks200ResponseDataInner&gt;](ListWebhooks200ResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { ListWebhooks200Response } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
  "requestId": null,
} satisfies ListWebhooks200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListWebhooks200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


