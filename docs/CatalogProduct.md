
# CatalogProduct


## Properties

Name | Type
------------ | -------------
`externalId` | string
`title` | string
`handle` | string
`productType` | string
`vendor` | string
`tags` | Array&lt;string&gt;
`collections` | Array&lt;string&gt;
`url` | string

## Example

```typescript
import type { CatalogProduct } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "externalId": null,
  "title": null,
  "handle": null,
  "productType": null,
  "vendor": null,
  "tags": null,
  "collections": null,
  "url": null,
} satisfies CatalogProduct

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CatalogProduct
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


