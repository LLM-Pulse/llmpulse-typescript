
# OwnedMediaPlatformRollup


## Properties

Name | Type
------------ | -------------
`provider` | string
`connected` | boolean
`total` | number
`yours` | number
`sharePct` | number
`weekly` | [Array&lt;OwnedMediaPlatformRollupWeeklyInner&gt;](OwnedMediaPlatformRollupWeeklyInner.md)

## Example

```typescript
import type { OwnedMediaPlatformRollup } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "provider": null,
  "connected": null,
  "total": null,
  "yours": null,
  "sharePct": null,
  "weekly": null,
} satisfies OwnedMediaPlatformRollup

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaPlatformRollup
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


