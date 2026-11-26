
# AdRow

One row of /dimensions/ads. Fields depend on view: advertisers (domain, ads, executions, prompts, avg_position, best_position) and ads (id, model, title, snippet, url, domain, position, is_client, prompt_id, prompt_text, prompt_execution_id, executed_at).

## Properties

Name | Type
------------ | -------------
`domain` | string
`ads` | number
`executions` | number
`prompts` | number
`avgPosition` | number
`bestPosition` | number
`id` | number
`model` | string
`title` | string
`snippet` | string
`url` | string
`position` | number
`isClient` | boolean
`promptId` | number
`promptText` | string
`promptExecutionId` | number
`executedAt` | Date

## Example

```typescript
import type { AdRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "domain": null,
  "ads": null,
  "executions": null,
  "prompts": null,
  "avgPosition": null,
  "bestPosition": null,
  "id": null,
  "model": null,
  "title": null,
  "snippet": null,
  "url": null,
  "position": null,
  "isClient": null,
  "promptId": null,
  "promptText": null,
  "promptExecutionId": null,
  "executedAt": null,
} satisfies AdRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AdRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


