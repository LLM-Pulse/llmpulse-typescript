
# PromptDeleteResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`deleted` | boolean
`id` | number
`rawInput` | string
`totalAfter` | number
`requestId` | string

## Example

```typescript
import type { PromptDeleteResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "deleted": null,
  "id": null,
  "rawInput": null,
  "totalAfter": null,
  "requestId": null,
} satisfies PromptDeleteResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptDeleteResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


