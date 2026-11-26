
# RecommendationDetailResponseItemCounts

Items of the run per status, whatever item_status filters

## Properties

Name | Type
------------ | -------------
`active` | number
`completed` | number
`archived` | number

## Example

```typescript
import type { RecommendationDetailResponseItemCounts } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "active": null,
  "completed": null,
  "archived": null,
} satisfies RecommendationDetailResponseItemCounts

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RecommendationDetailResponseItemCounts
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


