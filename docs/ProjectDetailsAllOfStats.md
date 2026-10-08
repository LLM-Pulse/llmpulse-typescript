
# ProjectDetailsAllOfStats


## Properties

Name | Type
------------ | -------------
`promptsCount` | number
`promptsByBrandKind` | [ProjectDetailsAllOfStatsPromptsByBrandKind](ProjectDetailsAllOfStatsPromptsByBrandKind.md)
`competitorsCount` | number
`collectionsCount` | number

## Example

```typescript
import type { ProjectDetailsAllOfStats } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "promptsCount": null,
  "promptsByBrandKind": null,
  "competitorsCount": null,
  "collectionsCount": null,
} satisfies ProjectDetailsAllOfStats

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetailsAllOfStats
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


