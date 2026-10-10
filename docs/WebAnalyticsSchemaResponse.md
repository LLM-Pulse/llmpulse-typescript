
# WebAnalyticsSchemaResponse


## Properties

Name | Type
------------ | -------------
`projectId` | number
`provider` | string
`property` | string
`queryLanguage` | string
`docsUrl` | string
`allowedFields` | Array&lt;string&gt;
`rules` | Array&lt;string&gt;
`example` | { [key: string]: any; }
`fields` | { [key: string]: any; }
`fieldsUnavailable` | string
`requestId` | string

## Example

```typescript
import type { WebAnalyticsSchemaResponse } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "projectId": null,
  "provider": null,
  "property": null,
  "queryLanguage": null,
  "docsUrl": null,
  "allowedFields": null,
  "rules": null,
  "example": null,
  "fields": null,
  "fieldsUnavailable": null,
  "requestId": null,
} satisfies WebAnalyticsSchemaResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WebAnalyticsSchemaResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


