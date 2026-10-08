
# SummaryResponseAllOfSummaryValueInner


## Properties

Name | Type
------------ | -------------
`actor` | [Actor](Actor.md)
`metric` | string
`total` | number
`aggregation` | string
`min` | number
`max` | number
`last` | number

## Example

```typescript
import type { SummaryResponseAllOfSummaryValueInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "actor": null,
  "metric": null,
  "total": null,
  "aggregation": null,
  "min": null,
  "max": null,
  "last": null,
} satisfies SummaryResponseAllOfSummaryValueInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SummaryResponseAllOfSummaryValueInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


