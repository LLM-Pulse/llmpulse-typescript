
# AiTrafficResponse

Visits from AI assistants measured by the connected web analytics provider, by day over the window.

## Properties

Name | Type
------------ | -------------
`projectId` | number
`provider` | string
`from` | Date
`to` | Date
`granularity` | string
`totals` | [AiTrafficResponseTotals](AiTrafficResponseTotals.md)
`bySource` | [Array&lt;AiTrafficResponseBySourceInner&gt;](AiTrafficResponseBySourceInner.md)
`timeseries` | { [key: string]: { [key: string]: number; }; }
`requestId` | string

## Example

```typescript
import type { AiTrafficResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "provider": null,
  "from": null,
  "to": null,
  "granularity": null,
  "totals": null,
  "bySource": null,
  "timeseries": null,
  "requestId": null,
} satisfies AiTrafficResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AiTrafficResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


