
# PeecExportImportResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`importId` | number
`status` | string
`prompts` | number
`newPrompts` | number
`plannedAnswers` | number
`models` | { [key: string]: string; }
`skippedModels` | Array&lt;string&gt;
`detectedBrands` | Array&lt;string&gt;
`appUrl` | string
`requestId` | string

## Example

```typescript
import type { PeecExportImportResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "importId": null,
  "status": null,
  "prompts": null,
  "newPrompts": null,
  "plannedAnswers": null,
  "models": null,
  "skippedModels": null,
  "detectedBrands": null,
  "appUrl": null,
  "requestId": null,
} satisfies PeecExportImportResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PeecExportImportResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


