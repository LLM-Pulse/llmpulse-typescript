
# RecommendationDetailResponse

One recommendation run with its items

## Properties

Name | Type
------------ | -------------
`id` | number
`projectId` | number
`recommendationType` | string
`status` | string
`errorMessage` | string
`generatedAt` | Date
`createdAt` | Date
`updatedAt` | Date
`totalRecommendations` | number
`highPriorityCount` | number
`summary` | [RecommendationDetailResponseSummary](RecommendationDetailResponseSummary.md)
`context` | object
`reportData` | { [key: string]: any; }
`itemCounts` | [RecommendationDetailResponseItemCounts](RecommendationDetailResponseItemCounts.md)
`items` | [Array&lt;RecommendationItem&gt;](RecommendationItem.md)
`requestId` | string

## Example

```typescript
import type { RecommendationDetailResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "projectId": null,
  "recommendationType": null,
  "status": null,
  "errorMessage": null,
  "generatedAt": null,
  "createdAt": null,
  "updatedAt": null,
  "totalRecommendations": null,
  "highPriorityCount": null,
  "summary": null,
  "context": null,
  "reportData": null,
  "itemCounts": null,
  "items": null,
  "requestId": null,
} satisfies RecommendationDetailResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RecommendationDetailResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


