
# UrlListFilters

The filters the numbers were read with.

## Properties

Name | Type
------------ | -------------
`model` | string
`collectionId` | string
`countryCode` | string
`languageCode` | string
`prompt` | number
`brandKind` | string
`from` | string
`to` | string

## Example

```typescript
import type { UrlListFilters } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "model": null,
  "collectionId": null,
  "countryCode": null,
  "languageCode": null,
  "prompt": null,
  "brandKind": null,
  "from": null,
  "to": null,
} satisfies UrlListFilters

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListFilters
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


