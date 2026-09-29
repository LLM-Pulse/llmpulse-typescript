
# LlmsTxtTechnicalGeoReport

An llms_txt technical GEO report with its files, in the shape GET /technical_geo_reports/{id} returns

## Properties

Name | Type
------------ | -------------
`id` | number
`reportType` | string
`projectId` | number
`batchId` | number
`url` | string
`domain` | string
`countryCode` | string
`outputLanguageCode` | string
`status` | string
`resultAvailable` | boolean
`overallScore` | number
`createdAt` | Date
`updatedAt` | Date
`resultData` | [LlmsTxtTechnicalGeoReportResultData](LlmsTxtTechnicalGeoReportResultData.md)
`errorMessage` | string
`pollAfterSeconds` | number
`appUrl` | string
`requestId` | string

## Example

```typescript
import type { LlmsTxtTechnicalGeoReport } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "reportType": null,
  "projectId": null,
  "batchId": null,
  "url": null,
  "domain": null,
  "countryCode": null,
  "outputLanguageCode": null,
  "status": null,
  "resultAvailable": null,
  "overallScore": null,
  "createdAt": null,
  "updatedAt": null,
  "resultData": null,
  "errorMessage": null,
  "pollAfterSeconds": null,
  "appUrl": null,
  "requestId": null,
} satisfies LlmsTxtTechnicalGeoReport

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as LlmsTxtTechnicalGeoReport
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


