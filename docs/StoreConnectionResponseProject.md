
# StoreConnectionResponseProject

The live project the store maps to: its domain equals the store\'s, or is a parent or subdomain of it. Null when no project matches

## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`domain` | string
`countryCode` | string
`languageCode` | string

## Example

```typescript
import type { StoreConnectionResponseProject } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "domain": null,
  "countryCode": null,
  "languageCode": null,
} satisfies StoreConnectionResponseProject

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as StoreConnectionResponseProject
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


