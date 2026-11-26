
# CitationSeries

The answers citing it under the same filters, by AI model and per period of the account tracking cadence

## Properties

Name | Type
------------ | -------------
`granularity` | string
`total` | number
`byModel` | { [key: string]: number; }
`data` | [Array&lt;AiModelPositionDistributionBrandBucketsInnerDataInner&gt;](AiModelPositionDistributionBrandBucketsInnerDataInner.md)

## Example

```typescript
import type { CitationSeries } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "granularity": null,
  "total": null,
  "byModel": null,
  "data": null,
} satisfies CitationSeries

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationSeries
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


