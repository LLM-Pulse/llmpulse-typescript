
# SearchConsoleOpportunitiesResponse


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
`minImpressions` | number
`minPosition` | number
`maxPosition` | number
`topCtr` | number
`page` | number
`perPage` | number
`total` | number
`truncated` | boolean
`data` | [Array&lt;SearchConsoleOpportunitiesResponseDataInner&gt;](SearchConsoleOpportunitiesResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { SearchConsoleOpportunitiesResponse } from '@llmpulse/sdk'

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
  "minImpressions": null,
  "minPosition": null,
  "maxPosition": null,
  "topCtr": null,
  "page": null,
  "perPage": null,
  "total": null,
  "truncated": null,
  "data": null,
  "requestId": null,
} satisfies SearchConsoleOpportunitiesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchConsoleOpportunitiesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


