
# UrlListEntry


## Properties

Name | Type
------------ | -------------
`id` | number
`value` | string
`matchType` | string
`host` | string
`status` | string
`addedOn` | Date
`cost` | number
`channel` | string
`citations` | number
`citedPages` | number
`firstCitedAt` | Date
`lastCitedAt` | Date
`daysToFirstCitation` | number
`avgCitationPosition` | number
`models` | Array&lt;string&gt;
`brandMentioned` | boolean

## Example

```typescript
import type { UrlListEntry } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "value": null,
  "matchType": null,
  "host": null,
  "status": null,
  "addedOn": null,
  "cost": null,
  "channel": null,
  "citations": null,
  "citedPages": null,
  "firstCitedAt": null,
  "lastCitedAt": null,
  "daysToFirstCitation": null,
  "avgCitationPosition": null,
  "models": null,
  "brandMentioned": null,
} satisfies UrlListEntry

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListEntry
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


