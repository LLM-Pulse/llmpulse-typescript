
# OwnedMediaCitedItemStats

The counts the platform reports for the item; absent keys are unknown

## Properties

Name | Type
------------ | -------------
`citations` | number
`likes` | number
`comments` | number
`views` | number
`followers` | number
`uniquePosts` | number
`uniqueVideos` | number

## Example

```typescript
import type { OwnedMediaCitedItemStats } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "citations": null,
  "likes": null,
  "comments": null,
  "views": null,
  "followers": null,
  "uniquePosts": null,
  "uniqueVideos": null,
} satisfies OwnedMediaCitedItemStats

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaCitedItemStats
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


