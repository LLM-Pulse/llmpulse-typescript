
# CmsContentItemResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`site` | [CmsSite](CmsSite.md)
`data` | [CmsContentItem](CmsContentItem.md)
`requestId` | string

## Example

```typescript
import type { CmsContentItemResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "site": null,
  "data": null,
  "requestId": null,
} satisfies CmsContentItemResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CmsContentItemResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


