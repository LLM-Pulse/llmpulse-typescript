
# Actor


## Properties

Name | Type
------------ | -------------
`type` | string
`id` | number
`competitorId` | number
`name` | string
`domain` | string

## Example

```typescript
import type { Actor } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "type": null,
  "id": null,
  "competitorId": null,
  "name": null,
  "domain": null,
} satisfies Actor

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Actor
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


