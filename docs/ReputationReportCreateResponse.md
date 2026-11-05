
# ReputationReportCreateResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`created` | boolean
`report` | [ReputationReportSummary](ReputationReportSummary.md)
`requestId` | string

## Example

```typescript
import type { ReputationReportCreateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "created": null,
  "report": null,
  "requestId": null,
} satisfies ReputationReportCreateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReputationReportCreateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


