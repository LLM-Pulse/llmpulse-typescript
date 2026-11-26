
# CitedUrlDetailsResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`urlSha256` | string
`url` | string
`normalizedUrl` | string
`domain` | string
`host` | string
`stats` | [CitedUrlDetailsResponseStats](CitedUrlDetailsResponseStats.md)
`urls` | Array&lt;string | null&gt;
`pageDetails` | [CitationPageDetails](CitationPageDetails.md)
`citationSeries` | [CitationSeries](CitationSeries.md)
`requestId` | string

## Example

```typescript
import type { CitedUrlDetailsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "urlSha256": null,
  "url": null,
  "normalizedUrl": null,
  "domain": null,
  "host": null,
  "stats": null,
  "urls": null,
  "pageDetails": null,
  "citationSeries": null,
  "requestId": null,
} satisfies CitedUrlDetailsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitedUrlDetailsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


