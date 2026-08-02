
# UpdateAnnotationRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`title` | string
`description` | string
`annotationDate` | Date
`color` | string
`annotationCategoryId` | number

## Example

```typescript
import type { UpdateAnnotationRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "title": null,
  "description": null,
  "annotationDate": null,
  "color": null,
  "annotationCategoryId": null,
} satisfies UpdateAnnotationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateAnnotationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


