
# PromptsCreateRequest


## Properties

Name | Type
------------ | -------------
`projectId` | number
`prompts` | Array&lt;string&gt;
`countryCode` | string
`languageCode` | string

## Example

```typescript
import type { PromptsCreateRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "prompts": null,
  "countryCode": null,
  "languageCode": null,
} satisfies PromptsCreateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PromptsCreateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


