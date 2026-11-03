
# AccountExecutionQuota

The account\'s allowance of AI answers for the current tracking window: its prompt limit times its enabled AI models, plus 5% so prompts can be replaced during the window. Every scheduled run and every first run of a new prompt spends one answer per AI model, and deleting a prompt gives nothing back. When it is used up, new prompts wait until resets_at. limit and remaining are null when unlimited is true. For a key limited to some projects, only remaining and unlimited (the account-wide answers left), period and resets_at.

## Properties

Name | Type
------------ | -------------
`limit` | number
`used` | number
`remaining` | number
`unlimited` | boolean
`period` | string
`resetsAt` | Date

## Example

```typescript
import type { AccountExecutionQuota } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "limit": null,
  "used": null,
  "remaining": null,
  "unlimited": null,
  "period": null,
  "resetsAt": null,
} satisfies AccountExecutionQuota

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccountExecutionQuota
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


