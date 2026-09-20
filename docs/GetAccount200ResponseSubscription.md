
# GetAccount200ResponseSubscription

Billing state. Present only for callers who can access Billing and Plans in the app; absent otherwise.

## Properties

Name | Type
------------ | -------------
`status` | string
`trialing` | boolean
`currentPeriodEndsAt` | Date

## Example

```typescript
import type { GetAccount200ResponseSubscription } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "trialing": null,
  "currentPeriodEndsAt": null,
} satisfies GetAccount200ResponseSubscription

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetAccount200ResponseSubscription
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


