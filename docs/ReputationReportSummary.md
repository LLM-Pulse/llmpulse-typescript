
# ReputationReportSummary

One reputation report\'s status and analyst model coverage

## Properties

Name | Type
------------ | -------------
`id` | string
`status` | string
`createdAt` | Date
`processedAt` | Date
`availableModels` | Array&lt;string&gt;
`missingModels` | Array&lt;string&gt;
`errorMessage` | string

## Example

```typescript
import type { ReputationReportSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "status": null,
  "createdAt": null,
  "processedAt": null,
  "availableModels": null,
  "missingModels": null,
  "errorMessage": null,
} satisfies ReputationReportSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReputationReportSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


