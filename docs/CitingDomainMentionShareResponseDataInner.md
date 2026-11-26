
# CitingDomainMentionShareResponseDataInner


## Properties

Name | Type
------------ | -------------
`domain` | string
`responsesCiting` | number
`totalMentions` | number
`actors` | [Array&lt;CitingDomainMentionShareResponseDataInnerActorsInner&gt;](CitingDomainMentionShareResponseDataInnerActorsInner.md)

## Example

```typescript
import type { CitingDomainMentionShareResponseDataInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "domain": null,
  "responsesCiting": null,
  "totalMentions": null,
  "actors": null,
} satisfies CitingDomainMentionShareResponseDataInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitingDomainMentionShareResponseDataInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


