
# CollectionCreateResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`collection` | [CollectionCreateResponseCollection](CollectionCreateResponseCollection.md)
`promptsAttached` | number
`totalCollections` | number
`requestId` | string

## Example

```typescript
import type { CollectionCreateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "collection": null,
  "promptsAttached": null,
  "totalCollections": null,
  "requestId": null,
} satisfies CollectionCreateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CollectionCreateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


