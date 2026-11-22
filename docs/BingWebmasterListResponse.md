
# BingWebmasterListResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`site` | string
`syncStatus` | string
`lastSyncedAt` | Date
`historyCurrent` | boolean
`from` | Date
`to` | Date
`dataThrough` | Date
`page` | number
`perPage` | number
`total` | number
`sort` | string
`weeksCovered` | number
`data` | [Array&lt;BingWebmasterListResponseDataInner&gt;](BingWebmasterListResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { BingWebmasterListResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "site": null,
  "syncStatus": null,
  "lastSyncedAt": null,
  "historyCurrent": null,
  "from": null,
  "to": null,
  "dataThrough": null,
  "page": null,
  "perPage": null,
  "total": null,
  "sort": null,
  "weeksCovered": null,
  "data": null,
  "requestId": null,
} satisfies BingWebmasterListResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BingWebmasterListResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


