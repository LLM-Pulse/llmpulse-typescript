
# AiOverviewResultsResponseByPrompt

One row per prompt with an AI Overview run in the window, highest result rate first, then more runs and the prompt id

## Properties

Name | Type
------------ | -------------
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;AiOverviewResultsResponseByPromptDataInner&gt;](AiOverviewResultsResponseByPromptDataInner.md)

## Example

```typescript
import type { AiOverviewResultsResponseByPrompt } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
} satisfies AiOverviewResultsResponseByPrompt

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiOverviewResultsResponseByPrompt
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


