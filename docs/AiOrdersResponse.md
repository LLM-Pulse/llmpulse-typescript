
# AiOrdersResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`platform` | string
`currency` | string
`from` | Date
`to` | Date
`totals` | [AiOrdersResponseTotals](AiOrdersResponseTotals.md)
`bySource` | [Array&lt;AiOrdersResponseBySourceInner&gt;](AiOrdersResponseBySourceInner.md)
`series` | [Array&lt;AiOrdersResponseSeriesInner&gt;](AiOrdersResponseSeriesInner.md)
`requestId` | string

## Example

```typescript
import type { AiOrdersResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "platform": null,
  "currency": null,
  "from": null,
  "to": null,
  "totals": null,
  "bySource": null,
  "series": null,
  "requestId": null,
} satisfies AiOrdersResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiOrdersResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


