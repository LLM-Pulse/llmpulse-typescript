
# AiModelSentimentRow


## Properties

Name | Type
------------ | -------------
`model` | string
`label` | string
`color` | string
`sentimentsCount` | number
`positiveCount` | number
`negativeCount` | number
`netSentiment` | number

## Example

```typescript
import type { AiModelSentimentRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "model": null,
  "label": null,
  "color": null,
  "sentimentsCount": null,
  "positiveCount": null,
  "negativeCount": null,
  "netSentiment": null,
} satisfies AiModelSentimentRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelSentimentRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


