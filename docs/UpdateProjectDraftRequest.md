
# UpdateProjectDraftRequest


## Properties

Name | Type
------------ | -------------
`step` | string
`name` | string
`brandName` | string
`description` | string
`industry` | Array&lt;string&gt;
`matchingNames` | Array&lt;string&gt;
`externalIdentifier` | string
`prompts` | Array&lt;string&gt;
`competitors` | Array&lt;object&gt;
`youtubeChannelUrl` | string
`instagramProfileUrl` | string
`facebookPageUrl` | string
`tiktokProfileUrl` | string
`appStoreUrl` | string
`googlePlayUrl` | string
`suggest` | boolean

## Example

```typescript
import type { UpdateProjectDraftRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "step": null,
  "name": null,
  "brandName": null,
  "description": null,
  "industry": null,
  "matchingNames": null,
  "externalIdentifier": null,
  "prompts": null,
  "competitors": null,
  "youtubeChannelUrl": null,
  "instagramProfileUrl": null,
  "facebookPageUrl": null,
  "tiktokProfileUrl": null,
  "appStoreUrl": null,
  "googlePlayUrl": null,
  "suggest": null,
} satisfies UpdateProjectDraftRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateProjectDraftRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


