
# UrlListEntryInput

An entry. A plain string is read as its value.

## Properties

Name | Type
------------ | -------------
`value` | string
`matchType` | string
`addedOn` | Date
`cost` | number
`channel` | string

## Example

```typescript
import type { UrlListEntryInput } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "value": null,
  "matchType": null,
  "addedOn": null,
  "cost": null,
  "channel": null,
} satisfies UrlListEntryInput

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListEntryInput
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


