
# CustomReportWidget


## Properties

Name | Type
------------ | -------------
`key` | string
`label` | string
`kind` | string
`width` | string
`available` | boolean
`data` | { [key: string]: any; }

## Example

```typescript
import type { CustomReportWidget } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "key": null,
  "label": null,
  "kind": null,
  "width": null,
  "available": null,
  "data": null,
} satisfies CustomReportWidget

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportWidget
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


