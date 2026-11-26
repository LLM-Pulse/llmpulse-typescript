
# CitedUrlContentResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`urlSha256` | string
`url` | string
`normalizedUrl` | string
`domain` | string
`host` | string
`pageDetails` | [CitationPageDetails](CitationPageDetails.md)
`requestId` | string

## Example

```typescript
import type { CitedUrlContentResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "urlSha256": null,
  "url": null,
  "normalizedUrl": null,
  "domain": null,
  "host": null,
  "pageDetails": null,
  "requestId": null,
} satisfies CitedUrlContentResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitedUrlContentResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


