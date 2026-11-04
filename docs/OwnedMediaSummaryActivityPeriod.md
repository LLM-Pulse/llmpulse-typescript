
# OwnedMediaSummaryActivityPeriod


## Properties

Name | Type
------------ | -------------
`date` | Date
`citations` | number
`yours` | number
`other` | number
`positive` | number
`neutral` | number
`negative` | number

## Example

```typescript
import type { OwnedMediaSummaryActivityPeriod } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "date": null,
  "citations": null,
  "yours": null,
  "other": null,
  "positive": null,
  "neutral": null,
  "negative": null,
} satisfies OwnedMediaSummaryActivityPeriod

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaSummaryActivityPeriod
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


