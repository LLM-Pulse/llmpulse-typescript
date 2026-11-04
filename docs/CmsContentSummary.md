
# CmsContentSummary


## Properties

Name | Type
------------ | -------------
`id` | number
`type` | string
`status` | string
`slug` | string
`title` | string
`url` | string
`modifiedAt` | Date

## Example

```typescript
import type { CmsContentSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "type": null,
  "status": null,
  "slug": null,
  "title": null,
  "url": null,
  "modifiedAt": null,
} satisfies CmsContentSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CmsContentSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


