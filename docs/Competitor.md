
# Competitor


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`domain` | string
`actorType` | string
`isOwn` | boolean

## Example

```typescript
import type { Competitor } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "domain": null,
  "actorType": null,
  "isOwn": null,
} satisfies Competitor

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as Competitor
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


