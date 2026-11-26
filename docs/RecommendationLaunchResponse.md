
# RecommendationLaunchResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`recommendation` | [RecommendationLaunchResponseRecommendation](RecommendationLaunchResponseRecommendation.md)
`requestId` | string

## Example

```typescript
import type { RecommendationLaunchResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "recommendation": null,
  "requestId": null,
} satisfies RecommendationLaunchResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RecommendationLaunchResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


