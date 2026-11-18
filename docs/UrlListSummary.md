
# UrlListSummary


## Properties

Name | Type
------------ | -------------
`entriesCount` | number
`citedEntries` | number
`citations` | number
`answers` | number
`citationRate` | number
`avgCitationPosition` | number
`medianDaysToFirstCitation` | number
`totalCost` | number
`costPerCitedEntry` | number

## Example

```typescript
import type { UrlListSummary } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "entriesCount": null,
  "citedEntries": null,
  "citations": null,
  "answers": null,
  "citationRate": null,
  "avgCitationPosition": null,
  "medianDaysToFirstCitation": null,
  "totalCost": null,
  "costPerCitedEntry": null,
} satisfies UrlListSummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UrlListSummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


