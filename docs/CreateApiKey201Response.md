
# CreateApiKey201Response


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`prefix` | string
`scope` | string
`projectScoped` | boolean
`projectIds` | Array&lt;number&gt;
`createdAt` | Date
`lastUsedAt` | Date
`revokedAt` | Date
`token` | string
`requestId` | string

## Example

```typescript
import type { CreateApiKey201Response } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "prefix": null,
  "scope": null,
  "projectScoped": null,
  "projectIds": null,
  "createdAt": null,
  "lastUsedAt": null,
  "revokedAt": null,
  "token": null,
  "requestId": null,
} satisfies CreateApiKey201Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateApiKey201Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


