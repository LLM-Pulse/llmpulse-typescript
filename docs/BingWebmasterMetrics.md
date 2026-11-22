
# BingWebmasterMetrics

Bing reports no average position in its daily totals.

## Properties

Name | Type
------------ | -------------
`impressions` | number
`clicks` | number
`ctr` | number

## Example

```typescript
import type { BingWebmasterMetrics } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "impressions": null,
  "clicks": null,
  "ctr": null,
} satisfies BingWebmasterMetrics

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BingWebmasterMetrics
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


