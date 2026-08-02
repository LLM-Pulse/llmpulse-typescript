
# AgentBot


## Properties

Name | Type
------------ | -------------
`slug` | string
`name` | string
`company` | string
`category` | string
`cfVerifiedCategory` | string
`description` | string

## Example

```typescript
import type { AgentBot } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "slug": null,
  "name": null,
  "company": null,
  "category": null,
  "cfVerifiedCategory": null,
  "description": null,
} satisfies AgentBot

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentBot
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


