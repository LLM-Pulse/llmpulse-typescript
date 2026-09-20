
# AccountCapacity

A ceiling with no usage counter attached. limit is null when unlimited is true.

## Properties

Name | Type
------------ | -------------
`limit` | number
`unlimited` | boolean

## Example

```typescript
import type { AccountCapacity } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "limit": null,
  "unlimited": null,
} satisfies AccountCapacity

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountCapacity
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


