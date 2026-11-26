
# AiModelPositionDistributionResponse

The positions at which one or two brands were mentioned, in four buckets, per period of the window.

## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`filters` | [AiModelInsightsReportFiltersEcho](AiModelInsightsReportFiltersEcho.md)
`granularity` | string
`brands` | [Array&lt;AiModelPositionDistributionBrand&gt;](AiModelPositionDistributionBrand.md)
`maxStackedValue` | number
`requestId` | string

## Example

```typescript
import type { AiModelPositionDistributionResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "filters": null,
  "granularity": null,
  "brands": null,
  "maxStackedValue": null,
  "requestId": null,
} satisfies AiModelPositionDistributionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiModelPositionDistributionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


