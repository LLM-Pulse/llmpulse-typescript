
# SummaryResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`granularity` | string
`filters` | [MetricsFiltersEcho](MetricsFiltersEcho.md)
`series` | { [key: string]: Array&lt;TimeseriesSeries&gt;; }
`requestId` | string
`summary` | { [key: string]: Array&lt;SummaryResponseAllOfSummaryValueInner&gt;; }
`positionDistribution` | [SummaryResponseAllOfPositionDistribution](SummaryResponseAllOfPositionDistribution.md)

## Example

```typescript
import type { SummaryResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "granularity": null,
  "filters": null,
  "series": null,
  "requestId": null,
  "summary": null,
  "positionDistribution": null,
} satisfies SummaryResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SummaryResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


