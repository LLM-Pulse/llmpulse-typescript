
# ProjectDeleteResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`deleted` | boolean
`name` | string
`url` | string
`note` | string
`requestId` | string

## Example

```typescript
import type { ProjectDeleteResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "deleted": null,
  "name": null,
  "url": null,
  "note": null,
  "requestId": null,
} satisfies ProjectDeleteResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDeleteResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


