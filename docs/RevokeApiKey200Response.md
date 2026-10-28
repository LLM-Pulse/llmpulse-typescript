
# RevokeApiKey200Response


## Properties

Name | Type
------------ | -------------
`revoked` | boolean
`id` | number
`revokedAt` | Date
`requestId` | string

## Example

```typescript
import type { RevokeApiKey200Response } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "revoked": null,
  "id": null,
  "revokedAt": null,
  "requestId": null,
} satisfies RevokeApiKey200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RevokeApiKey200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


