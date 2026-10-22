
# SearchConsolePropertyError


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`code` | string
`message` | string
`retryAfter` | number

## Example

```typescript
import type { SearchConsolePropertyError } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "code": null,
  "message": null,
  "retryAfter": null,
} satisfies SearchConsolePropertyError

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchConsolePropertyError
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


