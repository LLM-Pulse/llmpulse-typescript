
# TimeseriesSeries


## Properties

Name | Type
------------ | -------------
`actor` | [Actor](Actor.md)
`metric` | string
`data` | [Array&lt;TimeseriesPoint&gt;](TimeseriesPoint.md)

## Example

```typescript
import type { TimeseriesSeries } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "actor": null,
  "metric": null,
  "data": null,
} satisfies TimeseriesSeries

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TimeseriesSeries
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


