
# SummaryResponseAllOfPositionDistribution


## Properties

Name | Type
------------ | -------------
`position1Count` | number
`position2Count` | number
`position3PlusCount` | number
`totalMentions` | number
`percentages` | object

## Example

```typescript
import type { SummaryResponseAllOfPositionDistribution } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "position1Count": null,
  "position2Count": null,
  "position3PlusCount": null,
  "totalMentions": null,
  "percentages": null,
} satisfies SummaryResponseAllOfPositionDistribution

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SummaryResponseAllOfPositionDistribution
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


