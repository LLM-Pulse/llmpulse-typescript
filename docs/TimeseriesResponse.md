
# TimeseriesResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`granularity` | string
`filters` | object
`series` | { [key: string]: Array&lt;TimeseriesSeries&gt;; }
`requestId` | string

## Example

```typescript
import type { TimeseriesResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "granularity": null,
  "filters": null,
  "series": null,
  "requestId": null,
} satisfies TimeseriesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TimeseriesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


