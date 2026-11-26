
# ProjectDraftRecord


## Properties

Name | Type
------------ | -------------
`draftId` | string
`status` | string
`currentStep` | string
`stepsCompleted` | Array&lt;string&gt;
`stepsRemaining` | Array&lt;string&gt;
`optionalSteps` | Array&lt;string&gt;
`finalizable` | boolean
`websiteUrl` | string
`mainCountry` | string
`mainLanguage` | string
`useSubdomain` | boolean
`name` | string
`brandName` | string
`description` | string
`industry` | Array&lt;string&gt;
`matchingNames` | Array&lt;string&gt;
`prompts` | Array&lt;string&gt;
`competitors` | [Array&lt;ProjectDraftRecordCompetitorsInner&gt;](ProjectDraftRecordCompetitorsInner.md)
`ownedMedia` | [ProjectDraftRecordOwnedMedia](ProjectDraftRecordOwnedMedia.md)
`weeklyEmailSubscribed` | boolean
`externalIdentifier` | string
`executePromptsImmediately` | boolean
`projectId` | number
`expiresAt` | Date
`createdAt` | Date

## Example

```typescript
import type { ProjectDraftRecord } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "draftId": null,
  "status": null,
  "currentStep": null,
  "stepsCompleted": null,
  "stepsRemaining": null,
  "optionalSteps": null,
  "finalizable": null,
  "websiteUrl": null,
  "mainCountry": null,
  "mainLanguage": null,
  "useSubdomain": null,
  "name": null,
  "brandName": null,
  "description": null,
  "industry": null,
  "matchingNames": null,
  "prompts": null,
  "competitors": null,
  "ownedMedia": null,
  "weeklyEmailSubscribed": null,
  "externalIdentifier": null,
  "executePromptsImmediately": null,
  "projectId": null,
  "expiresAt": null,
  "createdAt": null,
} satisfies ProjectDraftRecord

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDraftRecord
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


