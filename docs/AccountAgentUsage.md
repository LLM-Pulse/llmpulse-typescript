
# AccountAgentUsage

The share of this calendar month\'s allowance for the in-app AI assistant (Europe/Madrid) that the account\'s team has used, owner and members together; each embedded project has an allowance of its own, left out here. The allowance is published as a share only, never as an amount; longer questions and bigger analyses use more of it. Deleting conversations gives nothing back.

## Properties

Name | Type
------------ | -------------
`percentUsed` | number
`unlimited` | boolean
`included` | boolean
`period` | string
`resetsOn` | Date

## Example

```typescript
import type { AccountAgentUsage } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "percentUsed": null,
  "unlimited": null,
  "included": null,
  "period": null,
  "resetsOn": null,
} satisfies AccountAgentUsage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountAgentUsage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


