
# ShoppingRow

One row of /dimensions/shopping. Fields depend on view: products (product_key, title, domain, url, merchants, currency, currency_count, min_price, max_price, avg_rating, rating_votes, appearances, is_client, best_rank, models, last_seen_at) and merchants (merchant, appearances, products, currency, min_price, max_price, avg_price, avg_rating).

## Properties

Name | Type
------------ | -------------
`productKey` | string
`title` | string
`domain` | string
`url` | string
`merchants` | string
`merchant` | string
`products` | number
`currency` | string
`currencyCount` | number
`minPrice` | number
`maxPrice` | number
`avgPrice` | number
`avgRating` | number
`ratingVotes` | number
`appearances` | number
`isClient` | boolean
`bestRank` | number
`models` | Array&lt;string&gt;
`lastSeenAt` | Date

## Example

```typescript
import type { ShoppingRow } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "productKey": null,
  "title": null,
  "domain": null,
  "url": null,
  "merchants": null,
  "merchant": null,
  "products": null,
  "currency": null,
  "currencyCount": null,
  "minPrice": null,
  "maxPrice": null,
  "avgPrice": null,
  "avgRating": null,
  "ratingVotes": null,
  "appearances": null,
  "isClient": null,
  "bestRank": null,
  "models": null,
  "lastSeenAt": null,
} satisfies ShoppingRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ShoppingRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


