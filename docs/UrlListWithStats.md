
# UrlListWithStats


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`description` | string
`currency` | string
`createdAt` | Date
`updatedAt` | Date
`entriesCount` | number
`citedEntries` | number
`citations` | number
`lastCitedAt` | Date

## Example

```typescript
import type { UrlListWithStats } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "currency": null,
  "createdAt": null,
  "updatedAt": null,
  "entriesCount": null,
  "citedEntries": null,
  "citations": null,
  "lastCitedAt": null,
} satisfies UrlListWithStats

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListWithStats
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


