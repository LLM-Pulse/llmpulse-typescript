
# SearchConsoleTimeseriesResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`property` | [SearchConsoleProperty](SearchConsoleProperty.md)
`from` | Date
`to` | Date
`dataThrough` | Date
`granularity` | string
`data` | [Array&lt;SearchConsoleTimeseriesResponseDataInner&gt;](SearchConsoleTimeseriesResponseDataInner.md)
`requestId` | string
`properties` | [Array&lt;SearchConsoleProperty&gt;](SearchConsoleProperty.md)
`excludedProperties` | [Array&lt;SearchConsoleExcludedProperty&gt;](SearchConsoleExcludedProperty.md)
`propertyErrors` | [Array&lt;SearchConsolePropertyError&gt;](SearchConsolePropertyError.md)

## Example

```typescript
import type { SearchConsoleTimeseriesResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "property": null,
  "from": null,
  "to": null,
  "dataThrough": null,
  "granularity": null,
  "data": null,
  "requestId": null,
  "properties": null,
  "excludedProperties": null,
  "propertyErrors": null,
} satisfies SearchConsoleTimeseriesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchConsoleTimeseriesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


