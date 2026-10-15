
# SuggestedPrompt


## Properties

Name | Type
------------ | -------------
`id` | number
`prompt` | string
`source` | string
`status` | string
`countryCode` | string
`languageCode` | string
`promptId` | number
`acceptedAt` | Date
`createdAt` | Date

## Example

```typescript
import type { SuggestedPrompt } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "prompt": null,
  "source": null,
  "status": null,
  "countryCode": null,
  "languageCode": null,
  "promptId": null,
  "acceptedAt": null,
  "createdAt": null,
} satisfies SuggestedPrompt

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SuggestedPrompt
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


