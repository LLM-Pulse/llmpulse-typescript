
# ProjectProfile

The project name and profile, as PATCH /projects/{id} and the update_project MCP tool return them

## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`brandName` | string
`description` | string
`industry` | any
`businessModel` | string
`businessModelOther` | string
`targetAudience` | string
`primaryProducts` | Array&lt;string&gt;
`brandVoice` | string
`goals` | string
`matchingNames` | Array&lt;string&gt;
`additionalOwnedDomains` | Array&lt;string&gt;

## Example

```typescript
import type { ProjectProfile } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "brandName": null,
  "description": null,
  "industry": null,
  "businessModel": null,
  "businessModelOther": null,
  "targetAudience": null,
  "primaryProducts": null,
  "brandVoice": null,
  "goals": null,
  "matchingNames": null,
  "additionalOwnedDomains": null,
} satisfies ProjectProfile

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectProfile
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


