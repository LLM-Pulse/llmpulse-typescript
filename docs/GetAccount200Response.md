
# GetAccount200Response


## Properties

Name | Type
------------ | -------------
`plan` | string
`trackingFrequency` | string
`role` | string
`subscription` | [GetAccount200ResponseSubscription](GetAccount200ResponseSubscription.md)
`limits` | [GetAccount200ResponseLimits](GetAccount200ResponseLimits.md)
`rateLimits` | [GetAccount200ResponseRateLimits](GetAccount200ResponseRateLimits.md)
`requestId` | string

## Example

```typescript
import type { GetAccount200Response } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "plan": null,
  "trackingFrequency": null,
  "role": null,
  "subscription": null,
  "limits": null,
  "rateLimits": null,
  "requestId": null,
} satisfies GetAccount200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetAccount200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


