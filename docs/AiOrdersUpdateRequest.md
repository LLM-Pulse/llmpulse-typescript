
# AiOrdersUpdateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`platform` | string
`currency` | string
`from` | Date
`to` | Date
`days` | [Array&lt;AiOrdersUpdateRequestDaysInner&gt;](AiOrdersUpdateRequestDaysInner.md)

## Example

```typescript
import type { AiOrdersUpdateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "platform": null,
  "currency": null,
  "from": null,
  "to": null,
  "days": null,
} satisfies AiOrdersUpdateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiOrdersUpdateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


