
# CitationRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`domain` | string
`promptId` | number
`promptExecutionId` | number
`url` | string
`position` | number
`createdAt` | Date

## Example

```typescript
import type { CitationRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "domain": null,
  "promptId": null,
  "promptExecutionId": null,
  "url": null,
  "position": null,
  "createdAt": null,
} satisfies CitationRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitationRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


