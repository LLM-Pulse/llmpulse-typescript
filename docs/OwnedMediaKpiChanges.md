
# OwnedMediaKpiChanges

Change against the previous period. Counts in percent, share_pct in percentage points; null when the previous period has nothing to compare with

## Properties

Name | Type
------------ | -------------
`total` | number
`yours` | number
`yourProfile` | number
`yourContent` | number
`sharePct` | number

## Example

```typescript
import type { OwnedMediaKpiChanges } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "total": null,
  "yours": null,
  "yourProfile": null,
  "yourContent": null,
  "sharePct": null,
} satisfies OwnedMediaKpiChanges

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaKpiChanges
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


