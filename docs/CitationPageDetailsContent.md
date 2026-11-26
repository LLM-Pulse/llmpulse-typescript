
# CitationPageDetailsContent

GET /citation_intelligence/urls/{url_sha256}/content only. Both null when the page has no usable content.

## Properties

Name | Type
------------ | -------------
`text` | string
`renderedHtml` | string

## Example

```typescript
import type { CitationPageDetailsContent } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "text": null,
  "renderedHtml": null,
} satisfies CitationPageDetailsContent

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationPageDetailsContent
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


