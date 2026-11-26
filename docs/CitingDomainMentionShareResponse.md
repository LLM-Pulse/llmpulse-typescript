
# CitingDomainMentionShareResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`filters` | [CitationIntelligenceFiltersEcho](CitationIntelligenceFiltersEcho.md)
`normalization` | string
`data` | [Array&lt;CitingDomainMentionShareResponseDataInner&gt;](CitingDomainMentionShareResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { CitingDomainMentionShareResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "filters": null,
  "normalization": null,
  "data": null,
  "requestId": null,
} satisfies CitingDomainMentionShareResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitingDomainMentionShareResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


