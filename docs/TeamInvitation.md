
# TeamInvitation


## Properties

Name | Type
------------ | -------------
`id` | number
`email` | string
`permissionRole` | string
`accountRole` | [TeamAccountRole](TeamAccountRole.md)
`permissions` | { [key: string]: Array&lt;string&gt;; }
`accountAdmin` | boolean
`billingAccess` | boolean
`allProjects` | boolean
`projectIds` | Array&lt;number&gt;
`invitedAt` | Date
`expiresAt` | Date
`createdAt` | Date

## Example

```typescript
import type { TeamInvitation } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "email": null,
  "permissionRole": null,
  "accountRole": null,
  "permissions": null,
  "accountAdmin": null,
  "billingAccess": null,
  "allProjects": null,
  "projectIds": null,
  "invitedAt": null,
  "expiresAt": null,
  "createdAt": null,
} satisfies TeamInvitation

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TeamInvitation
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


