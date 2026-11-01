
# ProjectDetailsAllOfPitchRun

The one run of a pitch project; null for a tracked project. Its answers are dated between launched_at and settled_at, so read its metrics with from set to the launched_at date (the default ranges leave out a pitch older than a few weeks)

## Properties

Name | Type
------------ | -------------
`status` | string
`launchedAt` | Date
`settledAt` | Date
`models` | Array&lt;string&gt;
`answersExpected` | number
`answersReceived` | number

## Example

```typescript
import type { ProjectDetailsAllOfPitchRun } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "launchedAt": null,
  "settledAt": null,
  "models": null,
  "answersExpected": null,
  "answersReceived": null,
} satisfies ProjectDetailsAllOfPitchRun

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetailsAllOfPitchRun
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


