
# AgentTrafficResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`from` | Date
`to` | Date
`groupBy` | string
`granularity` | string
`totals` | { [key: string]: number; }
`timeseries` | { [key: string]: { [key: string]: number; }; }
`requestId` | string

## Example

```typescript
import type { AgentTrafficResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "from": null,
  "to": null,
  "groupBy": null,
  "granularity": null,
  "totals": null,
  "timeseries": null,
  "requestId": null,
} satisfies AgentTrafficResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AgentTrafficResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


