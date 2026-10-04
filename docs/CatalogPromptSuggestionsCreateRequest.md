
# CatalogPromptSuggestionsCreateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`platform` | string
`countryCode` | string
`languageCode` | string
`products` | [Array&lt;CatalogProduct&gt;](CatalogProduct.md)

## Example

```typescript
import type { CatalogPromptSuggestionsCreateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "platform": null,
  "countryCode": null,
  "languageCode": null,
  "products": null,
} satisfies CatalogPromptSuggestionsCreateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CatalogPromptSuggestionsCreateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


