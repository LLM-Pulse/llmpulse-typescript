
# OwnedMediaSummaryResponsePrevious

The period of the same length that ends just before from

## Properties

Name | Type
------------ | -------------
`from` | Date
`to` | Date
`kpis` | [OwnedMediaKpis](OwnedMediaKpis.md)

## Example

```typescript
import type { OwnedMediaSummaryResponsePrevious } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "from": null,
  "to": null,
  "kpis": null,
} satisfies OwnedMediaSummaryResponsePrevious

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaSummaryResponsePrevious
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


