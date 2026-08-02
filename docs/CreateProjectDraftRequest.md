
# CreateProjectDraftRequest


## Properties

Name | Type
------------ | -------------
`websiteUrl` | string
`mainCountry` | string
`mainLanguage` | string
`useSubdomain` | boolean
`suggest` | boolean
`executePromptsImmediately` | boolean

## Example

```typescript
import type { CreateProjectDraftRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "websiteUrl": null,
  "mainCountry": null,
  "mainLanguage": null,
  "useSubdomain": null,
  "suggest": null,
  "executePromptsImmediately": null,
} satisfies CreateProjectDraftRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateProjectDraftRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


