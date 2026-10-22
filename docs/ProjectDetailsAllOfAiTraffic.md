
# ProjectDetailsAllOfAiTraffic

Web analytics provider behind /metrics/ai_traffic and /web_analytics. connected means both answer; reconnect_required means the provider refused the stored access, so /metrics/ai_traffic still answers from synced data and /web_analytics returns ERR_WEB_ANALYTICS_ACCESS_REVOKED until it is reconnected at connect_url; not_connected means they return ERR_AI_TRAFFIC_NOT_CONNECTED and ERR_WEB_ANALYTICS_NOT_CONNECTED.

## Properties

Name | Type
------------ | -------------
`status` | string
`provider` | string
`connectUrl` | string

## Example

```typescript
import type { ProjectDetailsAllOfAiTraffic } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "provider": null,
  "connectUrl": null,
} satisfies ProjectDetailsAllOfAiTraffic

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetailsAllOfAiTraffic
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


