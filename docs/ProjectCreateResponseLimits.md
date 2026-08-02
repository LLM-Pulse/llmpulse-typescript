
# ProjectCreateResponseLimits


## Properties

Name | Type
------------ | -------------
`projectsRemaining` | number
`promptsAvailable` | number
`competitorsRemaining` | number

## Example

```typescript
import type { ProjectCreateResponseLimits } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectsRemaining": null,
  "promptsAvailable": null,
  "competitorsRemaining": null,
} satisfies ProjectCreateResponseLimits

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectCreateResponseLimits
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


