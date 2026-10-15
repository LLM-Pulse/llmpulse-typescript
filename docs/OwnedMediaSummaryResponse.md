
# OwnedMediaSummaryResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`provider` | string
`from` | Date
`to` | Date
`connected` | boolean
`kpis` | [OwnedMediaKpis](OwnedMediaKpis.md)
`previous` | [OwnedMediaSummaryResponsePrevious](OwnedMediaSummaryResponsePrevious.md)
`changes` | [OwnedMediaKpiChanges](OwnedMediaKpiChanges.md)
`weekly` | [Array&lt;OwnedMediaWeek&gt;](OwnedMediaWeek.md)
`byModel` | [Array&lt;OwnedMediaModelShare&gt;](OwnedMediaModelShare.md)
`byCountry` | [Array&lt;OwnedMediaCountryShare&gt;](OwnedMediaCountryShare.md)
`contentTypes` | [Array&lt;OwnedMediaContentTypeShare&gt;](OwnedMediaContentTypeShare.md)
`ageBuckets` | [Array&lt;OwnedMediaAgeBucketShare&gt;](OwnedMediaAgeBucketShare.md)
`stores` | [Array&lt;OwnedMediaStoreTotals&gt;](OwnedMediaStoreTotals.md)
`platforms` | [Array&lt;OwnedMediaPlatformRollup&gt;](OwnedMediaPlatformRollup.md)
`requestId` | string

## Example

```typescript
import type { OwnedMediaSummaryResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "provider": null,
  "from": null,
  "to": null,
  "connected": null,
  "kpis": null,
  "previous": null,
  "changes": null,
  "weekly": null,
  "byModel": null,
  "byCountry": null,
  "contentTypes": null,
  "ageBuckets": null,
  "stores": null,
  "platforms": null,
  "requestId": null,
} satisfies OwnedMediaSummaryResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaSummaryResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


