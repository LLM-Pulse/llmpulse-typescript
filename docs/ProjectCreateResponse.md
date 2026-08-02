
# ProjectCreateResponse


## Properties

Name | Type
------------ | -------------
`project` | object
`prompts` | [ProjectCreateResponsePrompts](ProjectCreateResponsePrompts.md)
`competitors` | [ProjectCreateResponseCompetitors](ProjectCreateResponseCompetitors.md)
`emailSubscription` | [ProjectCreateResponseEmailSubscription](ProjectCreateResponseEmailSubscription.md)
`limits` | [ProjectCreateResponseLimits](ProjectCreateResponseLimits.md)
`idempotent` | boolean
`requestId` | string

## Example

```typescript
import type { ProjectCreateResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "project": null,
  "prompts": null,
  "competitors": null,
  "emailSubscription": null,
  "limits": null,
  "idempotent": null,
  "requestId": null,
} satisfies ProjectCreateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectCreateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


