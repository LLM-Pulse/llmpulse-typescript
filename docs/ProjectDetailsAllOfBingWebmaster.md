
# ProjectDetailsAllOfBingWebmaster

Bing Webmaster Tools site behind /bing_webmaster. connected means its endpoints answer; reconnect_required means Bing refused the stored API key or the site is no longer verified, so the endpoints still answer from the data already synced, which stops updating until the site is reconnected at connect_url; not_connected means they return ERR_BING_WEBMASTER_NOT_CONNECTED.

## Properties

Name | Type
------------ | -------------
`status` | string
`site` | string
`lastSyncedAt` | Date
`connectUrl` | string

## Example

```typescript
import type { ProjectDetailsAllOfBingWebmaster } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "site": null,
  "lastSyncedAt": null,
  "connectUrl": null,
} satisfies ProjectDetailsAllOfBingWebmaster

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetailsAllOfBingWebmaster
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


