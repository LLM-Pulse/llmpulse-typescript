
# AiTrafficResponseBySourceInner


## Properties

Name | Type
------------ | -------------
`source` | string
`name` | string
`users` | number
`sessions` | number
`conversions` | number

## Example

```typescript
import type { AiTrafficResponseBySourceInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "source": null,
  "name": null,
  "users": null,
  "sessions": null,
  "conversions": null,
} satisfies AiTrafficResponseBySourceInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiTrafficResponseBySourceInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


