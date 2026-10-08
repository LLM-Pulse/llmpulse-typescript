
# CompetitorCreateResponseCompetitor


## Properties

Name | Type
------------ | -------------
`id` | number
`brandName` | string
`domain` | string
`citationMatchMode` | [CitationMatchMode](CitationMatchMode.md)
`citationMatchPath` | string
`color` | string
`matchingNames` | Array&lt;string&gt;

## Example

```typescript
import type { CompetitorCreateResponseCompetitor } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "brandName": null,
  "domain": null,
  "citationMatchMode": null,
  "citationMatchPath": null,
  "color": null,
  "matchingNames": null,
} satisfies CompetitorCreateResponseCompetitor

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CompetitorCreateResponseCompetitor
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


