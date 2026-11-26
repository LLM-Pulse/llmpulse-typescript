
# ProjectDraftRecordOwnedMedia

The owned media fields the owned_media step sent; empty before it

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
import type { ProjectDraftRecordOwnedMedia } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "youtubeChannelUrl": null,
  "instagramProfileUrl": null,
  "facebookPageUrl": null,
  "tiktokProfileUrl": null,
  "appStoreUrl": null,
  "googlePlayUrl": null,
} satisfies ProjectDraftRecordOwnedMedia

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDraftRecordOwnedMedia
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


