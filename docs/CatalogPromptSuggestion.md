
# CatalogPromptSuggestion


## Properties

Name | Type
------------ | -------------
`id` | number
`prompt` | string
`status` | string
`source` | string
`countryCode` | string
`languageCode` | string
`product` | [CatalogPromptSuggestionProduct](CatalogPromptSuggestionProduct.md)
`promptId` | number
`acceptedAt` | Date
`createdAt` | Date

## Example

```typescript
import type { CatalogPromptSuggestion } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "prompt": null,
  "status": null,
  "source": null,
  "countryCode": null,
  "languageCode": null,
  "product": null,
  "promptId": null,
  "acceptedAt": null,
  "createdAt": null,
} satisfies CatalogPromptSuggestion

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CatalogPromptSuggestion
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


