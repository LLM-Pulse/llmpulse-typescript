
# SearchConsolePropertiesResponseDataInner


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`primary` | boolean
`type` | string
`status` | string
`lastSyncedAt` | Date

## Example

```typescript
import type { SearchConsolePropertiesResponseDataInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "primary": null,
  "type": null,
  "status": null,
  "lastSyncedAt": null,
} satisfies SearchConsolePropertiesResponseDataInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchConsolePropertiesResponseDataInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


