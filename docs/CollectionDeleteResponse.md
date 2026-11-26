
# CollectionDeleteResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`deleted` | boolean
`id` | number
`name` | string
`promptsKept` | number
`totalCollections` | number
`requestId` | string

## Example

```typescript
import type { CollectionDeleteResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "deleted": null,
  "id": null,
  "name": null,
  "promptsKept": null,
  "totalCollections": null,
  "requestId": null,
} satisfies CollectionDeleteResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CollectionDeleteResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


