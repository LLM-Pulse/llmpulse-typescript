
# SovResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`periods` | [Array&lt;SovResponsePeriodsInner&gt;](SovResponsePeriodsInner.md)
`overTime` | [Array&lt;SovResponseOverTimeInner&gt;](SovResponseOverTimeInner.md)
`current` | [Array&lt;SovResponseCurrentInner&gt;](SovResponseCurrentInner.md)
`breakdown` | [Array&lt;SovResponseBreakdownInner&gt;](SovResponseBreakdownInner.md)
`others` | Array&lt;object&gt;

## Example

```typescript
import type { SovResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "periods": null,
  "overTime": null,
  "current": null,
  "breakdown": null,
  "others": null,
} satisfies SovResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SovResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


