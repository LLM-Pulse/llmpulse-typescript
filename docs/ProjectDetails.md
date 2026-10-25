
# ProjectDetails


## Properties

Name | Type
------------ | -------------
`id` | number
`name` | string
`brandName` | string
`tracked` | boolean
`untrackedReason` | string
`url` | string
`description` | string
`matchingNames` | Array&lt;string&gt;
`additionalOwnedDomains` | Array&lt;string&gt;
`industry` | any
`businessModel` | string
`businessModelOther` | string
`primaryProducts` | Array&lt;string&gt;
`targetAudience` | string
`brandVoice` | string
`goals` | string
`countryCode` | string
`languageCode` | string
`paused` | boolean
`googlePlayId` | string
`appStoreId` | string
`createdAt` | Date
`promptLimit` | number
`stats` | [ProjectDetailsAllOfStats](ProjectDetailsAllOfStats.md)
`dataCoverage` | [ProjectDetailsAllOfDataCoverage](ProjectDetailsAllOfDataCoverage.md)
`searchConsole` | [ProjectDetailsAllOfSearchConsole](ProjectDetailsAllOfSearchConsole.md)
`aiTraffic` | [ProjectDetailsAllOfAiTraffic](ProjectDetailsAllOfAiTraffic.md)
`agentTraffic` | [ProjectDetailsAllOfAgentTraffic](ProjectDetailsAllOfAgentTraffic.md)
`requestId` | string

## Example

```typescript
import type { ProjectDetails } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "brandName": null,
  "tracked": null,
  "untrackedReason": null,
  "url": null,
  "description": null,
  "matchingNames": null,
  "additionalOwnedDomains": null,
  "industry": null,
  "businessModel": null,
  "businessModelOther": null,
  "primaryProducts": null,
  "targetAudience": null,
  "brandVoice": null,
  "goals": null,
  "countryCode": null,
  "languageCode": null,
  "paused": null,
  "googlePlayId": null,
  "appStoreId": null,
  "createdAt": null,
  "promptLimit": null,
  "stats": null,
  "dataCoverage": null,
  "searchConsole": null,
  "aiTraffic": null,
  "agentTraffic": null,
  "requestId": null,
} satisfies ProjectDetails

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetails
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


