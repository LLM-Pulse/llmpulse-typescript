# AIModelInsightsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAiModelInsightsSummary**](AIModelInsightsApi.md#getaimodelinsightssummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary |
| [**getAiModelPositionDistribution**](AIModelInsightsApi.md#getaimodelpositiondistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison |
| [**getAiOverviewResults**](AIModelInsightsApi.md#getaioverviewresults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability |



## getAiModelInsightsSummary

> getAiModelInsightsSummary(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors)

AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape &#x60;{ type, id, competitor_id, name, domain }&#x60; with bare (scheme-less) domains.

### Example

```ts
import {
  Configuration,
  AIModelInsightsApi,
} from '@llmpulse/sdk';
import type { GetAiModelInsightsSummaryRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIModelInsightsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
  } satisfies GetAiModelInsightsSummaryRequest;

  try {
    const data = await api.getAiModelInsightsSummary(body);
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
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAiModelPositionDistribution

> getAiModelPositionDistribution(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2)

Position distribution comparison

### Example

```ts
import {
  Configuration,
  AIModelInsightsApi,
} from '@llmpulse/sdk';
import type { GetAiModelPositionDistributionRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIModelInsightsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | 'naver_ai' | 'baidu_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // number | Competitor ID for the first comparison brand (omit to compare project brand) (optional)
    brand1: 56,
    // number (optional)
    brand2: 56,
  } satisfies GetAiModelPositionDistributionRequest;

  try {
    const data = await api.getAiModelPositionDistribution(body);
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
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus`, `naver_ai`, `baidu_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **brand1** | `number` | Competitor ID for the first comparison brand (omit to compare project brand) | [Optional] [Defaults to `undefined`] |
| **brand2** | `number` |  | [Optional] [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bucketed position totals + chart-ready series |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAiOverviewResults

> getAiOverviewResults(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage)

Google AI Overview result availability

### Example

```ts
import {
  Configuration,
  AIModelInsightsApi,
} from '@llmpulse/sdk';
import type { GetAiOverviewResultsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIModelInsightsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies GetAiOverviewResultsRequest;

  try {
    const data = await api.getAiOverviewResults(body);
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
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AI Overview result-availability data + per-prompt table |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

