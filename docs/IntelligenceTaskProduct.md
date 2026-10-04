
# IntelligenceTaskProduct

The store product a product_listing task rewrites

## Properties

Name | Type
------------ | -------------
`externalId` | string
`title` | string
`descriptionHtml` | string
`seoTitle` | string
`seoDescription` | string
`url` | string
`productType` | string
`images` | [Array&lt;IntelligenceTaskProductImagesInner&gt;](IntelligenceTaskProductImagesInner.md)

## Example

```typescript
import type { IntelligenceTaskProduct } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "externalId": null,
  "title": null,
  "descriptionHtml": null,
  "seoTitle": null,
  "seoDescription": null,
  "url": null,
  "productType": null,
  "images": null,
} satisfies IntelligenceTaskProduct

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IntelligenceTaskProduct
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


