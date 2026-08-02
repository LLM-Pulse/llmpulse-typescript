
# AgentBotsResponse


## Properties

Name | Type
------------ | -------------
`bots` | [Array&lt;AgentBot&gt;](AgentBot.md)
`companies` | Array&lt;string&gt;
`requestId` | string

## Example

```typescript
import type { AgentBotsResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "bots": null,
  "companies": null,
  "requestId": null,
} satisfies AgentBotsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentBotsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


