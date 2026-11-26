
# AnalystScoreRow

One analyst model\'s score of one brand (a subject in a custom study) on one attribute of one dimension

## Properties

Name | Type
------------ | -------------
`brand` | string
`isProject` | boolean
`model` | string
`reportDate` | Date
`dimension` | string
`dimensionName` | string
`attribute` | string
`attributeName` | string
`score` | any
`reasoning` | string

## Example

```typescript
import type { AnalystScoreRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "brand": null,
  "isProject": null,
  "model": null,
  "reportDate": null,
  "dimension": null,
  "dimensionName": null,
  "attribute": null,
  "attributeName": null,
  "score": null,
  "reasoning": null,
} satisfies AnalystScoreRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AnalystScoreRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


