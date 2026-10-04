
# AccountQuota

A consumable quota. limit and remaining are null when unlimited is true. For a key limited to some projects, prompts and intelligence_tasks carry no limit (and intelligence_tasks no used): only the capacity left.

## Properties

Name | Type
------------ | -------------
`limit` | number
`used` | number
`remaining` | number
`unlimited` | boolean
`period` | string

## Example

```typescript
import type { AccountQuota } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "limit": null,
  "used": null,
  "remaining": null,
  "unlimited": null,
  "period": null,
} satisfies AccountQuota

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountQuota
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


