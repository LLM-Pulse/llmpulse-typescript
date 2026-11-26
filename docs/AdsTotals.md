
# AdsTotals


## Properties

Name | Type
------------ | -------------
`ads` | number
`advertisers` | number
`yourAds` | number
`yourShare` | number
`avgPosition` | number
`executionsWithAds` | number

## Example

```typescript
import type { AdsTotals } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "ads": null,
  "advertisers": null,
  "yourAds": null,
  "yourShare": null,
  "avgPosition": null,
  "executionsWithAds": null,
} satisfies AdsTotals

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AdsTotals
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


