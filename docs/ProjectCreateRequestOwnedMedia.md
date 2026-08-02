
# ProjectCreateRequestOwnedMedia

Requires Growth plan or above

## Properties

Name | Type
------------ | -------------
`youtubeChannelUrl` | string
`instagramProfileUrl` | string
`facebookPageUrl` | string
`tiktokProfileUrl` | string
`appStoreUrl` | string
`googlePlayUrl` | string

## Example

```typescript
import type { ProjectCreateRequestOwnedMedia } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "youtubeChannelUrl": null,
  "instagramProfileUrl": null,
  "facebookPageUrl": null,
  "tiktokProfileUrl": null,
  "appStoreUrl": null,
  "googlePlayUrl": null,
} satisfies ProjectCreateRequestOwnedMedia

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectCreateRequestOwnedMedia
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


