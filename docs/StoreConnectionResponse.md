
# StoreConnectionResponse


## Properties

Name | Type
------------ | -------------
`platform` | string
`domain` | string
`project` | [StoreConnectionResponseProject](StoreConnectionResponseProject.md)
`ambiguous` | boolean
`candidates` | [Array&lt;StoreConnectionResponseCandidatesInner&gt;](StoreConnectionResponseCandidatesInner.md)
`account` | [StoreConnectionResponseAccount](StoreConnectionResponseAccount.md)
`requestId` | string

## Example

```typescript
import type { StoreConnectionResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "platform": null,
  "domain": null,
  "project": null,
  "ambiguous": null,
  "candidates": null,
  "account": null,
  "requestId": null,
} satisfies StoreConnectionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as StoreConnectionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


