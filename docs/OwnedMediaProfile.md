
# OwnedMediaProfile


## Properties

Name | Type
------------ | -------------
`url` | string
`handle` | string
`kind` | string
`main` | boolean
`store` | string
`name` | string
`avatarUrl` | string
`scrapeStatus` | string

## Example

```typescript
import type { OwnedMediaProfile } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "url": null,
  "handle": null,
  "kind": null,
  "main": null,
  "store": null,
  "name": null,
  "avatarUrl": null,
  "scrapeStatus": null,
} satisfies OwnedMediaProfile

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaProfile
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


