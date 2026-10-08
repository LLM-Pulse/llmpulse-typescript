
# AnnotationCreateResponseAnnotation


## Properties

Name | Type
------------ | -------------
`id` | number
`title` | string
`annotationDate` | Date
`description` | string
`color` | string
`annotationCategoryId` | number

## Example

```typescript
import type { AnnotationCreateResponseAnnotation } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": null,
  "annotationDate": null,
  "description": null,
  "color": null,
  "annotationCategoryId": null,
} satisfies AnnotationCreateResponseAnnotation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AnnotationCreateResponseAnnotation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


