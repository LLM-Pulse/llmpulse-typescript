# SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listSentimentRecords**](SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records |



## listSentimentRecords

> listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records

### Example

```ts
import {
  Configuration,
  SentimentsApi,
} from '@llmpulse/sdk';
import type { ListSentimentRecordsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SentimentsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    competitorId: 56,
    // boolean (optional)
    brandOnly: true,
    // 'very_positive' | 'positive' | 'neutral' | 'negative' | 'very_negative' (optional)
    analysis: analysis_example,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // number (optional)
    collectionId: 56,
    // string | ISO country code (e.g. US, GB, DE) (optional)
    countryCode: countryCode_example,
    // string | ISO language code (e.g. en, es, de) (optional)
    languageCode: languageCode_example,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date (optional)
    to: 2013-10-20T19:20:30+01:00,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListSentimentRecordsRequest;

  try {
    const data = await api.listSentimentRecords(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **projectId** | `number` | Project ID | [Defaults to `undefined`] |
| **competitorId** | `number` |  | [Optional] [Defaults to `undefined`] |
| **brandOnly** | `boolean` |  | [Optional] [Defaults to `undefined`] |
| **analysis** | `very_positive`, `positive`, `neutral`, `negative`, `very_negative` |  | [Optional] [Defaults to `undefined`] [Enum: very_positive, positive, neutral, negative, very_negative] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | `number` |  | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | ISO country code (e.g. US, GB, DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | ISO language code (e.g. en, es, de) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated sentiments |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

