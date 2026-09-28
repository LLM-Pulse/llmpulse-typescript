
# UpdateProjectRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`brandName` | string
`description` | string
`industry` | string
`businessModel` | string
`businessModelOther` | string
`targetAudience` | string
`brandVoice` | string
`goals` | string
`primaryProducts` | Array&lt;string&gt;
`matchingNames` | Array&lt;string&gt;

## Example

```typescript
import type { UpdateProjectRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "name": null,
  "brandName": null,
  "description": null,
  "industry": null,
  "businessModel": null,
  "businessModelOther": null,
  "targetAudience": null,
  "brandVoice": null,
  "goals": null,
  "primaryProducts": null,
  "matchingNames": null,
} satisfies UpdateProjectRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateProjectRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


