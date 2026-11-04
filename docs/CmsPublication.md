
# CmsPublication


## Properties

Name | Type
------------ | -------------
`id` | number
`platform` | string
`siteUrl` | string
`status` | string
`title` | string
`slug` | string
`sourceUrl` | string
`remoteId` | number
`remoteStatus` | string
`remoteUrl` | string
`editUrl` | string
`errorCode` | string
`createdAt` | Date
`sentAt` | Date

## Example

```typescript
import type { CmsPublication } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "platform": null,
  "siteUrl": null,
  "status": null,
  "title": null,
  "slug": null,
  "sourceUrl": null,
  "remoteId": null,
  "remoteStatus": null,
  "remoteUrl": null,
  "editUrl": null,
  "errorCode": null,
  "createdAt": null,
  "sentAt": null,
} satisfies CmsPublication

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CmsPublication
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


