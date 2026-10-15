
# RecommendationItem

One recommendation item, in the shape GET /recommendations/{id} lists items

## Properties

Name | Type
------------ | -------------
`id` | number
`recommendationId` | number
`recommendationType` | string
`category` | string
`title` | string
`description` | string
`priority` | string
`estimatedImpact` | string
`actionItems` | Array&lt;string&gt;
`sourceRefs` | Array&lt;string&gt;
`status` | string
`statusChangedAt` | Date
`position` | number
`metadata` | { [key: string]: any; }
`createdAt` | Date
`updatedAt` | Date
`resolvedSourceRefs` | Array&lt;{ [key: string]: any; }&gt;
`unresolvedSourceRefs` | Array&lt;string&gt;

## Example

```typescript
import type { RecommendationItem } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "recommendationId": null,
  "recommendationType": null,
  "category": null,
  "title": null,
  "description": null,
  "priority": null,
  "estimatedImpact": null,
  "actionItems": null,
  "sourceRefs": null,
  "status": null,
  "statusChangedAt": null,
  "position": null,
  "metadata": null,
  "createdAt": null,
  "updatedAt": null,
  "resolvedSourceRefs": null,
  "unresolvedSourceRefs": null,
} satisfies RecommendationItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RecommendationItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


