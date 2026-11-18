
# AiModelDeclinedAnswersResponseByPrompt

One row per prompt with an answer in the window, highest decline rate first, then more declines, more answers and the prompt id

## Properties

Name | Type
------------ | -------------
`page` | number
`perPage` | number
`total` | number
`data` | [Array&lt;AiModelDeclinedAnswersResponseByPromptDataInner&gt;](AiModelDeclinedAnswersResponseByPromptDataInner.md)

## Example

```typescript
import type { AiModelDeclinedAnswersResponseByPrompt } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "page": null,
  "perPage": null,
  "total": null,
  "data": null,
} satisfies AiModelDeclinedAnswersResponseByPrompt

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelDeclinedAnswersResponseByPrompt
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


