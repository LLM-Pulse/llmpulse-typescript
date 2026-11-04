
# RedditBrandShare


## Properties

Name | Type
------------ | -------------
`actorId` | number
`actorName` | string
`isBrand` | boolean
`citations` | number
`sharePct` | number

## Example

```typescript
import type { RedditBrandShare } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "actorId": null,
  "actorName": null,
  "isBrand": null,
  "citations": null,
  "sharePct": null,
} satisfies RedditBrandShare

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RedditBrandShare
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


