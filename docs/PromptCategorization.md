
# PromptCategorization


## Properties

Name | Type
------------ | -------------
`id` | number
`rawInput` | string
`promptType` | string
`brandKind` | string
`categorizationSource` | string
`manuallyCategorized` | boolean
`categorizedAt` | Date

## Example

```typescript
import type { PromptCategorization } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "rawInput": null,
  "promptType": null,
  "brandKind": null,
  "categorizationSource": null,
  "manuallyCategorized": null,
  "categorizedAt": null,
} satisfies PromptCategorization

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptCategorization
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


