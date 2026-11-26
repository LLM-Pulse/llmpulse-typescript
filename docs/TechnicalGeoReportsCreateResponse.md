
# TechnicalGeoReportsCreateResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`url` | string
`countryCode` | string
`outputLanguageCode` | string
`batchId` | number
`createdReports` | Array&lt;string&gt;
`reportIds` | { [key: string]: number; }
`appUrls` | { [key: string]: string; }
`failedReports` | [Array&lt;TechnicalGeoReportsCreateResponseFailedReportsInner&gt;](TechnicalGeoReportsCreateResponseFailedReportsInner.md)
`nextEndpoint` | string
`pollAfterSeconds` | number
`requestId` | string

## Example

```typescript
import type { TechnicalGeoReportsCreateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "url": null,
  "countryCode": null,
  "outputLanguageCode": null,
  "batchId": null,
  "createdReports": null,
  "reportIds": null,
  "appUrls": null,
  "failedReports": null,
  "nextEndpoint": null,
  "pollAfterSeconds": null,
  "requestId": null,
} satisfies TechnicalGeoReportsCreateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TechnicalGeoReportsCreateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


