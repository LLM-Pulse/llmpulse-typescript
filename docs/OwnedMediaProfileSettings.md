
# OwnedMediaProfileSettings

The current value of every field PATCH /projects/{id}/owned_media accepts

## Properties

Name | Type
------------ | -------------
`youtubeChannelUrl` | string
`appStoreUrl` | string
`googlePlayUrl` | string
`instagramProfileUrl` | string
`facebookPageUrl` | string
`tiktokProfileUrl` | string
`linkedinCompanyUrl` | string
`youtubeExtraProfileUrls` | Array&lt;string&gt;
`mobileAppsExtraProfileUrls` | Array&lt;string&gt;
`instagramExtraProfileUrls` | Array&lt;string&gt;
`facebookExtraProfileUrls` | Array&lt;string&gt;
`tiktokExtraProfileUrls` | Array&lt;string&gt;
`linkedinExtraProfileUrls` | Array&lt;string&gt;
`redditSubreddits` | Array&lt;string&gt;
`redditUsernames` | Array&lt;string&gt;

## Example

```typescript
import type { OwnedMediaProfileSettings } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "youtubeChannelUrl": null,
  "appStoreUrl": null,
  "googlePlayUrl": null,
  "instagramProfileUrl": null,
  "facebookPageUrl": null,
  "tiktokProfileUrl": null,
  "linkedinCompanyUrl": null,
  "youtubeExtraProfileUrls": null,
  "mobileAppsExtraProfileUrls": null,
  "instagramExtraProfileUrls": null,
  "facebookExtraProfileUrls": null,
  "tiktokExtraProfileUrls": null,
  "linkedinExtraProfileUrls": null,
  "redditSubreddits": null,
  "redditUsernames": null,
} satisfies OwnedMediaProfileSettings

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaProfileSettings
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


