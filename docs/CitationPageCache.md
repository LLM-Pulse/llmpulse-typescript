
# CitationPageCache

What was read on the cited page. Metadata is null when the page has no usable content.

## Properties

Name | Type
------------ | -------------
`present` | boolean
`lastCrawledAt` | Date
`statusCode` | number
`errorMessage` | string
`contentFormat` | string
`bytes` | number
`htmlTitle` | string
`metaTitle` | string
`metaDescription` | string
`h1` | string
`canonicalUrl` | string
`language` | string
`mentionsProcessed` | boolean
`contentAvailable` | boolean

## Example

```typescript
import type { CitationPageCache } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "present": null,
  "lastCrawledAt": null,
  "statusCode": null,
  "errorMessage": null,
  "contentFormat": null,
  "bytes": null,
  "htmlTitle": null,
  "metaTitle": null,
  "metaDescription": null,
  "h1": null,
  "canonicalUrl": null,
  "language": null,
  "mentionsProcessed": null,
  "contentAvailable": null,
} satisfies CitationPageCache

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationPageCache
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


