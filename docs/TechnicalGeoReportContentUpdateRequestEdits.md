
# TechnicalGeoReportContentUpdateRequestEdits

The files to replace, each mapped to its full replacement text: never blank, at most 200,000 characters. Send one file or both; a file identical to the stored one is ignored.

## Properties

Name | Type
------------ | -------------
`llmsTxt` | string
`llmsFullTxt` | string

## Example

```typescript
import type { TechnicalGeoReportContentUpdateRequestEdits } from '@llmpulse/sdk'

// TODO: Update the object below with actual values
const example = {
  "llmsTxt": null,
  "llmsFullTxt": null,
} satisfies TechnicalGeoReportContentUpdateRequestEdits

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TechnicalGeoReportContentUpdateRequestEdits
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


