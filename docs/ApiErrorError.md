
# ApiErrorError


## Properties

Name | Type
------------ | -------------
`code` | string
`message` | string
`meta` | object

## Example

```typescript
import type { ApiErrorError } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "code": null,
  "message": null,
  "meta": null,
} satisfies ApiErrorError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ApiErrorError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


