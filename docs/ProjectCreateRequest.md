
# ProjectCreateRequest


## Properties

Name | Type
------------ | -------------
`websiteUrl` | string
`name` | string
`mainCountry` | string
`mainLanguage` | string
`brandName` | string
`description` | string
`industry` | Array&lt;string&gt;
`matchingNames` | Array&lt;string&gt;
`prompts` | Array&lt;string&gt;
`competitors` | [Array&lt;ProjectCreateRequestCompetitorsInner&gt;](ProjectCreateRequestCompetitorsInner.md)
`ownedMedia` | [ProjectCreateRequestOwnedMedia](ProjectCreateRequestOwnedMedia.md)
`useSubdomain` | boolean
`weeklyEmailSubscribed` | boolean
`externalIdentifier` | string
`executePromptsImmediately` | boolean

## Example

```typescript
import type { ProjectCreateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "websiteUrl": https://acme.com,
  "name": Acme,
  "mainCountry": US,
  "mainLanguage": en,
  "brandName": null,
  "description": null,
  "industry": ["SAAS"],
  "matchingNames": null,
  "prompts": null,
  "competitors": null,
  "ownedMedia": null,
  "useSubdomain": null,
  "weeklyEmailSubscribed": null,
  "externalIdentifier": null,
  "executePromptsImmediately": null,
} satisfies ProjectCreateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectCreateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


