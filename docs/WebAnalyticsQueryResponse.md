
# WebAnalyticsQueryResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`provider` | string
`property` | string
`columns` | [Array&lt;WebAnalyticsQueryResponseColumnsInner&gt;](WebAnalyticsQueryResponseColumnsInner.md)
`rows` | Array&lt;Array&lt;any&gt;&gt;
`rowCount` | number
`totalRows` | number
`truncated` | boolean
`totals` | { [key: string]: any; }
`notes` | Array&lt;string&gt;
`meta` | { [key: string]: any; }
`fetchedAt` | Date
`cached` | boolean
`query` | { [key: string]: any; }
`requestId` | string

## Example

```typescript
import type { WebAnalyticsQueryResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "provider": null,
  "property": null,
  "columns": null,
  "rows": null,
  "rowCount": null,
  "totalRows": null,
  "truncated": null,
  "totals": null,
  "notes": null,
  "meta": null,
  "fetchedAt": null,
  "cached": null,
  "query": null,
  "requestId": null,
} satisfies WebAnalyticsQueryResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WebAnalyticsQueryResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


