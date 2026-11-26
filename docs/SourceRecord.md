
# SourceRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`promptExecutionId` | number
`domain` | string
`url` | string
`urlSha256` | string
`position` | number
`sourceType` | string
`isGooglePlayLink` | boolean
`isAppStoreLink` | boolean
`createdAt` | Date

## Example

```typescript
import type { SourceRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "promptExecutionId": null,
  "domain": null,
  "url": null,
  "urlSha256": null,
  "position": null,
  "sourceType": null,
  "isGooglePlayLink": null,
  "isAppStoreLink": null,
  "createdAt": null,
} satisfies SourceRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SourceRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


