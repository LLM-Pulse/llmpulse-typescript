
# CustomReportFilters


## Properties

Name | Type
------------ | -------------
`models` | Array&lt;string&gt;
`collectionIds` | Array&lt;number&gt;
`brandKind` | string
`competitorIds` | Array&lt;number&gt;

## Example

```typescript
import type { CustomReportFilters } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "models": null,
  "collectionIds": null,
  "brandKind": null,
  "competitorIds": null,
} satisfies CustomReportFilters

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CustomReportFilters
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


