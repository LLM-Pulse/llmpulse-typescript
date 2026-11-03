
# SearchConsoleBrandSplitResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`property` | [SearchConsoleProperty](SearchConsoleProperty.md)
`properties` | [Array&lt;SearchConsoleProperty&gt;](SearchConsoleProperty.md)
`excludedProperties` | [Array&lt;SearchConsoleExcludedProperty&gt;](SearchConsoleExcludedProperty.md)
`propertyErrors` | [Array&lt;SearchConsolePropertyError&gt;](SearchConsolePropertyError.md)
`from` | Date
`to` | Date
`dataThrough` | Date
`brandTerms` | Array&lt;string&gt;
`totals` | [SearchConsoleMetrics](SearchConsoleMetrics.md)
`branded` | [SearchConsoleMetrics](SearchConsoleMetrics.md)
`nonBranded` | [SearchConsoleMetrics](SearchConsoleMetrics.md)
`unclassified` | [SearchConsoleBrandSplitResponseUnclassified](SearchConsoleBrandSplitResponseUnclassified.md)
`requestId` | string

## Example

```typescript
import type { SearchConsoleBrandSplitResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "property": null,
  "properties": null,
  "excludedProperties": null,
  "propertyErrors": null,
  "from": null,
  "to": null,
  "dataThrough": null,
  "brandTerms": null,
  "totals": null,
  "branded": null,
  "nonBranded": null,
  "unclassified": null,
  "requestId": null,
} satisfies SearchConsoleBrandSplitResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchConsoleBrandSplitResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


