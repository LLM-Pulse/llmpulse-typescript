
# ProjectDetailsAllOfAgentTraffic

Agent traffic source behind /metrics/agent_traffic. connected and reconnect_required (the source refused the stored access, so syncing stopped) both answer from stored data; imported means no live source is connected but imported logs answer; not_connected means it returns ERR_AGENT_TRAFFIC_NOT_CONNECTED.

## Properties

Name | Type
------------ | -------------
`status` | string
`provider` | string
`connectUrl` | string

## Example

```typescript
import type { ProjectDetailsAllOfAgentTraffic } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "provider": null,
  "connectUrl": null,
} satisfies ProjectDetailsAllOfAgentTraffic

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetailsAllOfAgentTraffic
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


