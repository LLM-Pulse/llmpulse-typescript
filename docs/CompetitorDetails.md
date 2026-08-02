
# CompetitorDetails


## Properties

Name | Type
------------ | -------------
`id` | number
`projectId` | number
`brandName` | string
`domain` | string
`matchingNames` | Array&lt;string&gt;
`googlePlayId` | string
`appStoreId` | string
`color` | string
`createdAt` | Date

## Example

```typescript
import type { CompetitorDetails } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "projectId": null,
  "brandName": null,
  "domain": null,
  "matchingNames": null,
  "googlePlayId": null,
  "appStoreId": null,
  "color": null,
  "createdAt": null,
} satisfies CompetitorDetails

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CompetitorDetails
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


