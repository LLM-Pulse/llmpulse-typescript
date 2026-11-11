
# TrustpilotReplies

provider=trustpilot only. How the brand answers its Trustpilot reviews, on the profile of the project\'s own domain, among the reviews LLM Pulse holds for it (the newest ones from each monthly read, not every review on Trustpilot), whatever the date window. Every field is null until the profile has been read

## Properties

Name | Type
------------ | -------------
`reviewsHeld` | number
`repliedCount` | number
`notRepliedCount` | number
`replyRatePct` | number
`medianReplyHours` | number

## Example

```typescript
import type { TrustpilotReplies } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "reviewsHeld": null,
  "repliedCount": null,
  "notRepliedCount": null,
  "replyRatePct": null,
  "medianReplyHours": null,
} satisfies TrustpilotReplies

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TrustpilotReplies
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


