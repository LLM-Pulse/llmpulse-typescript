
# PromptRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`promptText` | string
`collectionId` | number
`collectionIds` | Array&lt;number&gt;
`tags` | [Array&lt;TagRef&gt;](TagRef.md)
`countryCode` | string
`languageCode` | string
`promptType` | string
`brandKind` | string
`lastExecutedAt` | Date
`appUrl` | string

## Example

```typescript
import type { PromptRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "promptText": null,
  "collectionId": null,
  "collectionIds": null,
  "tags": null,
  "countryCode": null,
  "languageCode": null,
  "promptType": null,
  "brandKind": null,
  "lastExecutedAt": null,
  "appUrl": null,
} satisfies PromptRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


