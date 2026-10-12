
# ProjectUpdateResponse


## Properties

Name | Type
------------ | -------------
`project` | [ProjectProfile](ProjectProfile.md)
`updatedFields` | Array&lt;string&gt;
`rematching` | boolean
`note` | string
`requestId` | string

## Example

```typescript
import type { ProjectUpdateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "project": null,
  "updatedFields": null,
  "rematching": null,
  "note": null,
  "requestId": null,
} satisfies ProjectUpdateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectUpdateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


