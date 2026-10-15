
# OwnedMediaCitingAnswer


## Properties

Name | Type
------------ | -------------
`answerId` | number
`promptId` | number
`promptText` | string
`model` | string
`countryCode` | string
`languageCode` | string
`executedAt` | Date
`excerpt` | string
`appUrl` | string

## Example

```typescript
import type { OwnedMediaCitingAnswer } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "answerId": null,
  "promptId": null,
  "promptText": null,
  "model": null,
  "countryCode": null,
  "languageCode": null,
  "executedAt": null,
  "excerpt": null,
  "appUrl": null,
} satisfies OwnedMediaCitingAnswer

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OwnedMediaCitingAnswer
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


