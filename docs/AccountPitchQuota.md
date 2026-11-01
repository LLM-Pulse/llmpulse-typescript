
# AccountPitchQuota

Pitch projects created this calendar month (Europe/Madrid) against the monthly allowance, which pitch projects use instead of a project slot. limit and remaining are null when unlimited is true.

## Properties

Name | Type
------------ | -------------
`limit` | number
`used` | number
`remaining` | number
`unlimited` | boolean
`period` | string
`resetsOn` | Date
`access` | string

## Example

```typescript
import type { AccountPitchQuota } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "limit": null,
  "used": null,
  "remaining": null,
  "unlimited": null,
  "period": null,
  "resetsOn": null,
  "access": null,
} satisfies AccountPitchQuota

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountPitchQuota
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


