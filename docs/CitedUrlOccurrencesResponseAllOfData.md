
# CitedUrlOccurrencesResponseAllOfData


## Properties

Name | Type
------------ | -------------
`sourceId` | number
`answerId` | number
`promptExecutionId` | number
`promptId` | number
`promptText` | string
`model` | string
`executedAt` | Date
`citationPosition` | number
`url` | string
`domain` | string
`sourceType` | string
`responseExcerpt` | string
`responseTruncated` | boolean
`fanOutQueries` | Array&lt;string&gt;

## Example

```typescript
import type { CitedUrlOccurrencesResponseAllOfData } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "sourceId": null,
  "answerId": null,
  "promptExecutionId": null,
  "promptId": null,
  "promptText": null,
  "model": null,
  "executedAt": null,
  "citationPosition": null,
  "url": null,
  "domain": null,
  "sourceType": null,
  "responseExcerpt": null,
  "responseTruncated": null,
  "fanOutQueries": null,
} satisfies CitedUrlOccurrencesResponseAllOfData

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitedUrlOccurrencesResponseAllOfData
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


