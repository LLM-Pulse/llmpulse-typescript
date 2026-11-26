
# QueryFanOutRow

A view=query row carries query_text, count and share; a view=prompt row carries prompt_id, prompt_text, variations_count and total_count

## Properties

Name | Type
------------ | -------------
`queryText` | string
`count` | number
`share` | number
`promptId` | number
`promptText` | string
`variationsCount` | number
`totalCount` | number

## Example

```typescript
import type { QueryFanOutRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "queryText": null,
  "count": null,
  "share": null,
  "promptId": null,
  "promptText": null,
  "variationsCount": null,
  "totalCount": null,
} satisfies QueryFanOutRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as QueryFanOutRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


