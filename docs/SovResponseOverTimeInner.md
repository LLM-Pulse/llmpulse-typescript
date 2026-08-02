
# SovResponseOverTimeInner


## Properties

Name | Type
------------ | -------------
`actor` | [Actor](Actor.md)
`data` | [Array&lt;TimeseriesPoint&gt;](TimeseriesPoint.md)

## Example

```typescript
import type { SovResponseOverTimeInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "actor": null,
  "data": null,
} satisfies SovResponseOverTimeInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SovResponseOverTimeInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


