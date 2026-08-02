
# Ping200Response


## Properties

Name | Type
------------ | -------------
`ok` | boolean
`userId` | number
`project` | [Project](Project.md)
`requestId` | string

## Example

```typescript
import type { Ping200Response } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "ok": null,
  "userId": null,
  "project": null,
  "requestId": null,
} satisfies Ping200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Ping200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


