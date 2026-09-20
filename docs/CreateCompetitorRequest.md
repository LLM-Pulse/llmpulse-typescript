
# CreateCompetitorRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`brandName` | string
`domain` | string
`matchingNames` | Array&lt;string&gt;
`citationMatchMode` | string
`citationMatchPath` | string

## Example

```typescript
import type { CreateCompetitorRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "brandName": null,
  "domain": null,
  "matchingNames": null,
  "citationMatchMode": null,
  "citationMatchPath": null,
} satisfies CreateCompetitorRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateCompetitorRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


