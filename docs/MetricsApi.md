# MetricsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getPromptSummary**](MetricsApi.md#getpromptsummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary |
| [**getShareOfVoice**](MetricsApi.md#getshareofvoice) | **GET** /metrics/sov | Share of Voice |
| [**getSummary**](MetricsApi.md#getsummary) | **GET** /metrics/summary | Aggregated metrics summary |
| [**getTimeseries**](MetricsApi.md#gettimeseries) | **GET** /metrics/timeseries | Time-series metrics |
| [**getTopSources**](MetricsApi.md#gettopsources) | **GET** /metrics/top_sources | Top cited sources |



## getPromptSummary

> PromptSummaryResponse getPromptSummary(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output)

Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass &#x60;breakdown&#x3D;model&#x60; to split each prompt by model.

### Example

```ts
import {
  Configuration,
  MetricsApi,
} from '@llmpulse/sdk';
import type { GetPromptSummaryRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MetricsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'model' | Add per-(prompt, model) rows to the output (optional)
    breakdown: breakdown_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // 'responses' | 'mentions' | 'citations' | 'mention_rate' | 'visibility' | 'citation_rate' | 'avg_mention_position' | 'avg_position' (optional)
    sort: sort_example,
    // 'asc' | 'desc' (optional)
    sortDir: sortDir_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies GetPromptSummaryRequest;

  try {
    const data = await api.getPromptSummary(body);
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
| **breakdown** | `model` | Add per-(prompt, model) rows to the output | [Optional] [Defaults to `undefined`] [Enum: model] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **sort** | `responses`, `mentions`, `citations`, `mention_rate`, `visibility`, `citation_rate`, `avg_mention_position`, `avg_position` |  | [Optional] [Defaults to `&#39;responses&#39;`] [Enum: responses, mentions, citations, mention_rate, visibility, citation_rate, avg_mention_position, avg_position] |
| **sortDir** | `asc`, `desc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**PromptSummaryResponse**](PromptSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-prompt metrics |  -  |
| **401** | Authentication failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getShareOfVoice

> SovResponse getShareOfVoice(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view)

Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Example

```ts
import {
  Configuration,
  MetricsApi,
} from '@llmpulse/sdk';
import type { GetShareOfVoiceRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MetricsApi(config);

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
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'over_time' | 'current' | 'breakdown' | Which Share of Voice projection to flatten. Only valid together with \'output\'. \'over_time\' (default) is one row per date and actor, \'current\' the ranked snapshot, \'breakdown\' the Top 4 plus Others. (optional)
    view: view_example,
  } satisfies GetShareOfVoiceRequest;

  try {
    const data = await api.getShareOfVoice(body);
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
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **view** | `over_time`, `current`, `breakdown` | Which Share of Voice projection to flatten. Only valid together with \&#39;output\&#39;. \&#39;over_time\&#39; (default) is one row per date and actor, \&#39;current\&#39; the ranked snapshot, \&#39;breakdown\&#39; the Top 4 plus Others. | [Optional] [Defaults to `&#39;over_time&#39;`] [Enum: over_time, current, breakdown] |

### Return type

[**SovResponse**](SovResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Share of voice data |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSummary

> SummaryResponse getSummary(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output)

Aggregated metrics summary

Same as /metrics/timeseries but adds a &#x60;summary&#x60; block with total/min/max/last per metric per actor, plus a &#x60;position_distribution&#x60; block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. &#x60;total&#x60; is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an &#x60;aggregation&#x60; field (&#x60;sum&#x60; or &#x60;average&#x60;).

### Example

```ts
import {
  Configuration,
  MetricsApi,
} from '@llmpulse/sdk';
import type { GetSummaryRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MetricsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. (optional)
    metrics: metrics_example,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies GetSummaryRequest;

  try {
    const data = await api.getSummary(body);
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
| **metrics** | `string` | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**SummaryResponse**](SummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary metrics |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTimeseries

> TimeseriesResponse getTimeseries(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output)

Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Example

```ts
import {
  Configuration,
  MetricsApi,
} from '@llmpulse/sdk';
import type { GetTimeseriesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MetricsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. (optional)
    metrics: metrics_example,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // boolean (optional)
    includeProject: true,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies GetTimeseriesRequest;

  try {
    const data = await api.getTimeseries(body);
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
| **metrics** | `string` | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **includeProject** | `boolean` |  | [Optional] [Defaults to `true`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**TimeseriesResponse**](TimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Time-series data |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTopSources

> TopSourcesResponse getTopSources(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output)

Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Example

```ts
import {
  Configuration,
  MetricsApi,
} from '@llmpulse/sdk';
import type { GetTopSourcesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MetricsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // 'total_responses' | 'avg_mention_rate' | 'avg_visibility' (optional)
    sort: sort_example,
    // string | Filter domains by case-insensitive partial match (optional)
    query: query_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies GetTopSourcesRequest;

  try {
    const data = await api.getTopSources(body);
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
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **sort** | `total_responses`, `avg_mention_rate`, `avg_visibility` |  | [Optional] [Defaults to `&#39;total_responses&#39;`] [Enum: total_responses, avg_mention_rate, avg_visibility] |
| **query** | `string` | Filter domains by case-insensitive partial match | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**TopSourcesResponse**](TopSourcesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top sources |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

