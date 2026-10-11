
# CreateTeamInvitationRequest


## Properties

Name | Type
------------ | -------------
`email` | string
`projectIds` | Array&lt;number&gt;
`allProjects` | boolean
`permissionRole` | string
`accountRoleId` | number
`permissions` | { [key: string]: Array&lt;string&gt;; }
`accountAdmin` | boolean
`billingAccess` | boolean

## Example

```typescript
import type { CreateTeamInvitationRequest } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "email": null,
  "projectIds": null,
  "allProjects": null,
  "permissionRole": null,
  "accountRoleId": null,
  "permissions": null,
  "accountAdmin": null,
  "billingAccess": null,
} satisfies CreateTeamInvitationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateTeamInvitationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


