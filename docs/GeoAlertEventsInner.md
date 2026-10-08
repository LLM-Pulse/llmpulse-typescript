
# GeoAlertEventsInner


## Properties

Name | Type
------------ | -------------
`kind` | string
`checkKey` | string
`subjectKey` | string
`severity` | string
`message` | string

## Example

```typescript
import type { GeoAlertEventsInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "kind": null,
  "checkKey": null,
  "subjectKey": null,
  "severity": null,
  "message": null,
} satisfies GeoAlertEventsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GeoAlertEventsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


