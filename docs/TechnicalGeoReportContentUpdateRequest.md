
# TechnicalGeoReportContentUpdateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`reportType` | string
`contentVersion` | string
`edits` | [TechnicalGeoReportContentUpdateRequestEdits](TechnicalGeoReportContentUpdateRequestEdits.md)

## Example

```typescript
import type { TechnicalGeoReportContentUpdateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "reportType": null,
  "contentVersion": 1790683200123456,
  "edits": null,
} satisfies TechnicalGeoReportContentUpdateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TechnicalGeoReportContentUpdateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


