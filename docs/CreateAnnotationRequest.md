
# CreateAnnotationRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`title` | string
`annotationDate` | Date
`description` | string
`color` | string
`annotationCategoryId` | number

## Example

```typescript
import type { CreateAnnotationRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "title": null,
  "annotationDate": null,
  "description": null,
  "color": null,
  "annotationCategoryId": null,
} satisfies CreateAnnotationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAnnotationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


