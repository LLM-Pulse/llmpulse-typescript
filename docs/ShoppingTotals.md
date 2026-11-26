
# ShoppingTotals


## Properties

Name | Type
------------ | -------------
`products` | number
`yourProducts` | number
`merchants` | number
`avgPrice` | number
`avgPriceCurrency` | string
`avgRating` | number
`executionsWithShopping` | number

## Example

```typescript
import type { ShoppingTotals } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "products": null,
  "yourProducts": null,
  "merchants": null,
  "avgPrice": null,
  "avgPriceCurrency": null,
  "avgRating": null,
  "executionsWithShopping": null,
} satisfies ShoppingTotals

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ShoppingTotals
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


