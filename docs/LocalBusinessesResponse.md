
# LocalBusinessesResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`page` | number
`perPage` | number
`total` | number
`totals` | [LocalBusinessesTotals](LocalBusinessesTotals.md)
`data` | [Array&lt;LocalBusiness&gt;](LocalBusiness.md)
`requestId` | string

## Example

```typescript
import type { LocalBusinessesResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "page": null,
  "perPage": null,
  "total": null,
  "totals": null,
  "data": null,
  "requestId": null,
} satisfies LocalBusinessesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as LocalBusinessesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


