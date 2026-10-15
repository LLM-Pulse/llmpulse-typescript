
# OwnedMediaWeek


## Properties

Name | Type
------------ | -------------
`week` | Date
`citations` | number
`yours` | number
`other` | number

## Example

```typescript
import type { OwnedMediaWeek } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "week": null,
  "citations": null,
  "yours": null,
  "other": null,
} satisfies OwnedMediaWeek

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaWeek
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


