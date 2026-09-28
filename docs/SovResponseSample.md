
# SovResponseSample

The period the current shares were computed on (the last one with mentions), same shape as a periods item; null when the window has no mentions.

## Properties

Name | Type
------------ | -------------
`date` | Date
`mentions` | number
`partial` | boolean
`confidence` | string
`marginOfError` | number

## Example

```typescript
import type { SovResponseSample } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "date": null,
  "mentions": null,
  "partial": null,
  "confidence": null,
  "marginOfError": null,
} satisfies SovResponseSample

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SovResponseSample
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


