
# LocalesResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`countries` | Array&lt;string&gt;
`languages` | Array&lt;string&gt;
`requestId` | string

## Example

```typescript
import type { LocalesResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "countries": null,
  "languages": null,
  "requestId": null,
} satisfies LocalesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as LocalesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


