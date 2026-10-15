
# PromptsImportRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`rows` | [Array&lt;PromptsImportRequestRowsInner&gt;](PromptsImportRequestRowsInner.md)

## Example

```typescript
import type { PromptsImportRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "rows": null,
} satisfies PromptsImportRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptsImportRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


