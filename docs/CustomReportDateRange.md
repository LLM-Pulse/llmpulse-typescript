
# CustomReportDateRange


## Properties

Name | Type
------------ | -------------
`type` | string
`rangeDays` | number
`from` | Date
`to` | Date
`label` | string

## Example

```typescript
import type { CustomReportDateRange } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "type": null,
  "rangeDays": null,
  "from": null,
  "to": null,
  "label": null,
} satisfies CustomReportDateRange

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportDateRange
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


