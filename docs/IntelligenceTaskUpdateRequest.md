
# IntelligenceTaskUpdateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`edits` | { [key: string]: string; }

## Example

```typescript
import type { IntelligenceTaskUpdateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "edits": {"title":"How to measure AI visibility in 2026","sections.0.content":"AI visibility is the share of AI answers that mention your brand."},
} satisfies IntelligenceTaskUpdateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IntelligenceTaskUpdateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


