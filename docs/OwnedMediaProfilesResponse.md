
# OwnedMediaProfilesResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`platforms` | [Array&lt;OwnedMediaPlatformProfiles&gt;](OwnedMediaPlatformProfiles.md)
`settings` | [OwnedMediaProfileSettings](OwnedMediaProfileSettings.md)
`requestId` | string

## Example

```typescript
import type { OwnedMediaProfilesResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "platforms": null,
  "settings": null,
  "requestId": null,
} satisfies OwnedMediaProfilesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaProfilesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


