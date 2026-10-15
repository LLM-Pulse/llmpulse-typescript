
# CompetitorSuggestion


## Properties

Name | Type
------------ | -------------
`id` | string
`domain` | string
`brandName` | string
`matchingNames` | Array&lt;string&gt;
`mentions` | number
`citations` | number

## Example

```typescript
import type { CompetitorSuggestion } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "domain": null,
  "brandName": null,
  "matchingNames": null,
  "mentions": null,
  "citations": null,
} satisfies CompetitorSuggestion

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CompetitorSuggestion
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


