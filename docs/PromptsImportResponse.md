
# PromptsImportResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`processedRows` | number
`created` | number
`duplicates` | number
`tagged` | number
`createdTags` | number
`rowErrors` | [Array&lt;PromptsImportResponseRowErrorsInner&gt;](PromptsImportResponseRowErrorsInner.md)
`lengthWarning` | string
`promptsAvailable` | number
`tracked` | boolean
`untrackedReason` | string
`warning` | string
`requestId` | string

## Example

```typescript
import type { PromptsImportResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "processedRows": null,
  "created": null,
  "duplicates": null,
  "tagged": null,
  "createdTags": null,
  "rowErrors": null,
  "lengthWarning": null,
  "promptsAvailable": null,
  "tracked": null,
  "untrackedReason": null,
  "warning": null,
  "requestId": null,
} satisfies PromptsImportResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptsImportResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


