
# CitedUrlDetailsResponseStats


## Properties

Name | Type
------------ | -------------
`totalResponses` | number
`totalCitations` | number
`citationRate` | number
`citationRateDenominator` | number
`avgCitationPosition` | number
`firstSeenAt` | Date
`lastSeenAt` | Date
`distinctUrls` | number
`sourceTypes` | [CitedUrlDetailsResponseStatsSourceTypes](CitedUrlDetailsResponseStatsSourceTypes.md)
`models` | { [key: string]: number; }

## Example

```typescript
import type { CitedUrlDetailsResponseStats } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "totalResponses": null,
  "totalCitations": null,
  "citationRate": null,
  "citationRateDenominator": null,
  "avgCitationPosition": null,
  "firstSeenAt": null,
  "lastSeenAt": null,
  "distinctUrls": null,
  "sourceTypes": null,
  "models": null,
} satisfies CitedUrlDetailsResponseStats

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CitedUrlDetailsResponseStats
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


