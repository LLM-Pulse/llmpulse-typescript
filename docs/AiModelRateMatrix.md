
# AiModelRateMatrix

Each actor\'s rate within each model: mentions of the actor (mentions_market_share), or answers citing it (citations_market_share), per answer of the model. Rates are independent, so the actors of a model can add up to more or less than 100.

## Properties

Name | Type
------------ | -------------
`denominatorsByModel` | { [key: string]: number; }
`actors` | [Array&lt;AiModelRateMatrixActor&gt;](AiModelRateMatrixActor.md)

## Example

```typescript
import type { AiModelRateMatrix } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "denominatorsByModel": null,
  "actors": null,
} satisfies AiModelRateMatrix

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelRateMatrix
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


