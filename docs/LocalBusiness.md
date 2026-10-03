
# LocalBusiness


## Properties

Name | Type
------------ | -------------
`businessKey` | string
`title` | string
`address` | string
`domain` | string
`url` | string
`phone` | string
`avgRating` | number
`reviews` | number
`avgPosition` | number
`prompts` | number
`appearances` | number
`isClient` | boolean
`competitorId` | number
`competitorName` | string

## Example

```typescript
import type { LocalBusiness } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "businessKey": null,
  "title": null,
  "address": null,
  "domain": null,
  "url": null,
  "phone": null,
  "avgRating": null,
  "reviews": null,
  "avgPosition": null,
  "prompts": null,
  "appearances": null,
  "isClient": null,
  "competitorId": null,
  "competitorName": null,
} satisfies LocalBusiness

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as LocalBusiness
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


