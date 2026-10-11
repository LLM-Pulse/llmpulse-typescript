
# ProjectDetailsAllOfSearchConsole

Google Search Console connection of the project. connected means the Search Console endpoints can answer; reconnect_required means Google refused the stored access and the property must be reconnected in Preferences > Project Settings > Data Connections.

## Properties

Name | Type
------------ | -------------
`status` | string
`property` | string

## Example

```typescript
import type { ProjectDetailsAllOfSearchConsole } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "property": null,
} satisfies ProjectDetailsAllOfSearchConsole

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectDetailsAllOfSearchConsole
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


