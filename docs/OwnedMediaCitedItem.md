
# OwnedMediaCitedItem

The post, video, profile or channel. Null when nothing in the window matches it

## Properties

Name | Type
------------ | -------------
`kind` | string
`title` | string
`subtitle` | string
`url` | string
`imageUrl` | string
`yours` | boolean
`date` | Date
`stats` | [OwnedMediaCitedItemStats](OwnedMediaCitedItemStats.md)

## Example

```typescript
import type { OwnedMediaCitedItem } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "kind": null,
  "title": null,
  "subtitle": null,
  "url": null,
  "imageUrl": null,
  "yours": null,
  "date": null,
  "stats": null,
} satisfies OwnedMediaCitedItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaCitedItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


