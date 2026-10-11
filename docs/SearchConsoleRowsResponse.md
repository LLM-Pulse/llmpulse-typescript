
# SearchConsoleRowsResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`property` | [SearchConsoleProperty](SearchConsoleProperty.md)
`from` | Date
`to` | Date
`dataThrough` | Date
`page` | number
`perPage` | number
`total` | number
`sort` | string
`startRow` | number
`truncated` | boolean
`dimensions` | Array&lt;string&gt;
`data` | [Array&lt;SearchConsoleRowsResponseDataInner&gt;](SearchConsoleRowsResponseDataInner.md)
`requestId` | string

## Example

```typescript
import type { SearchConsoleRowsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "property": null,
  "from": null,
  "to": null,
  "dataThrough": null,
  "page": null,
  "perPage": null,
  "total": null,
  "sort": null,
  "startRow": null,
  "truncated": null,
  "dimensions": null,
  "data": null,
  "requestId": null,
} satisfies SearchConsoleRowsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchConsoleRowsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


