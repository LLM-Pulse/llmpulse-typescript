
# AnnotationRecord


## Properties

Name | Type
------------ | -------------
`id` | number
`title` | string
`description` | string
`annotationDate` | Date
`color` | string
`category` | string
`origin` | string
`annotationCategory` | [AnnotationRecordAnnotationCategory](AnnotationRecordAnnotationCategory.md)
`editable` | boolean
`createdAt` | Date

## Example

```typescript
import type { AnnotationRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": null,
  "description": null,
  "annotationDate": null,
  "color": null,
  "category": null,
  "origin": null,
  "annotationCategory": null,
  "editable": null,
  "createdAt": null,
} satisfies AnnotationRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AnnotationRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


