
# CreateCollectionRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`name` | string
`description` | string
`promptIds` | Array&lt;number&gt;

## Example

```typescript
import type { CreateCollectionRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "name": null,
  "description": null,
  "promptIds": null,
} satisfies CreateCollectionRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateCollectionRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


