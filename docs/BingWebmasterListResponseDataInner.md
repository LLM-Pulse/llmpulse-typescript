
# BingWebmasterListResponseDataInner


## Properties

Name | Type
------------ | -------------
`key` | string
`impressions` | number
`clicks` | number
`ctr` | number
`avgImpressionPosition` | number
`avgClickPosition` | number

## Example

```typescript
import type { BingWebmasterListResponseDataInner } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "key": null,
  "impressions": null,
  "clicks": null,
  "ctr": null,
  "avgImpressionPosition": null,
  "avgClickPosition": null,
} satisfies BingWebmasterListResponseDataInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BingWebmasterListResponseDataInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


