
# OwnedMediaPlatformProfiles


## Properties

Name | Type
------------ | -------------
`platform` | string
`connected` | boolean
`maxExtraProfiles` | number
`profiles` | [Array&lt;OwnedMediaProfile&gt;](OwnedMediaProfile.md)

## Example

```typescript
import type { OwnedMediaPlatformProfiles } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "platform": null,
  "connected": null,
  "maxExtraProfiles": null,
  "profiles": null,
} satisfies OwnedMediaPlatformProfiles

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaPlatformProfiles
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


