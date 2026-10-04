
# AiOrdersResponseSeriesInner


## Properties

Name | Type
------------ | -------------
`day` | Date
`orders` | number
`revenue` | string

## Example

```typescript
import type { AiOrdersResponseSeriesInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "day": null,
  "orders": null,
  "revenue": null,
} satisfies AiOrdersResponseSeriesInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiOrdersResponseSeriesInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


