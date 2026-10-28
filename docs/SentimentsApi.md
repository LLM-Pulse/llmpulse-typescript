# SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getSentimentTags**](SentimentsApi.md#getsentimenttags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above) |
| [**getSentimentTopics**](SentimentsApi.md#getsentimenttopics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above) |
| [**listSentimentCategories**](SentimentsApi.md#listsentimentcategories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above) |
| [**listSentimentRecords**](SentimentsApi.md#listsentimentrecords) | **GET** /sentiments | List sentiment records (Growth plan or above) |



## getSentimentTags

> SentimentTagsResponse getSentimentTags(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output)

Sentiment by tag (Growth plan or above)

One row per tag of the project with at least one analyzed mention, with the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score. A mention counts once for every tag its prompt carries, as on the Sentiment page. Same filters as GET /reports/sentiment/topics. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```ts
import {
  Configuration,
  SentimentsApi,
} from '@llmpulse/sdk';
import type { GetSentimentTagsRequest } from '@llmpulse/sdk';

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
    // number | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | 'naver_ai_tab' | 'qwen' | 'doubao' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // string | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative (optional)
    analysis: analysis_example,
    // string | Only sentiments tagged with this topic (case-insensitive) (optional)
    topic: topic_example,
    // string | Only sentiments whose answer or prompt text contains this text (optional)
    query: query_example,
    // string | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). (optional)
    brand: brand_example,
    // 'mentions' | 'name' | 'positive' | 'negative' | 'neutral' | 'net_score' | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. (optional)
    sort: sort_example,
    // 'desc' | 'asc' (optional)
    sortDir: sortDir_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies GetSentimentTagsRequest;

  try {
    const data = await api.getSentimentTags(body);
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
| **range** | `number` | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai`, `naver_ai_tab`, `qwen`, `doubao` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **analysis** | `string` | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [Optional] [Defaults to `undefined`] |
| **topic** | `string` | Only sentiments tagged with this topic (case-insensitive) | [Optional] [Defaults to `undefined`] |
| **query** | `string` | Only sentiments whose answer or prompt text contains this text | [Optional] [Defaults to `undefined`] |
| **brand** | `string` | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [Optional] [Defaults to `undefined`] |
| **sort** | `mentions`, `name`, `positive`, `negative`, `neutral`, `net_score` | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [Optional] [Defaults to `&#39;mentions&#39;`] [Enum: mentions, name, positive, negative, neutral, net_score] |
| **sortDir** | `desc`, `asc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: desc, asc] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**SentimentTagsResponse**](SentimentTagsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tag rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSentimentTopics

> SentimentTopicsResponse getSentimentTopics(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output)

Sentiment by topic (Growth plan or above)

One row per topic AI answers associate with the brand (topics are matched case-insensitively), with its analyzed mentions, the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score ((positive - negative) / mentions x 100). The same rows and filters as the Topics tab of the Sentiment page: the window defaults to the last 28 days, &#x60;brand&#x60; empty counts your own brand, &#x60;all&#x60; every brand and a competitor id that competitor. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```ts
import {
  Configuration,
  SentimentsApi,
} from '@llmpulse/sdk';
import type { GetSentimentTopicsRequest } from '@llmpulse/sdk';

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
    // number | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | 'naver_ai_tab' | 'qwen' | 'doubao' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
    // string | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative (optional)
    analysis: analysis_example,
    // string | Only sentiments tagged with this topic (case-insensitive) (optional)
    topic: topic_example,
    // string | Only sentiments whose answer or prompt text contains this text (optional)
    query: query_example,
    // string | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). (optional)
    brand: brand_example,
    // 'mentions' | 'name' | 'positive' | 'negative' | 'neutral' | 'net_score' | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. (optional)
    sort: sort_example,
    // 'desc' | 'asc' (optional)
    sortDir: sortDir_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies GetSentimentTopicsRequest;

  try {
    const data = await api.getSentimentTopics(body);
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
| **range** | `number` | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai`, `naver_ai_tab`, `qwen`, `doubao` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **analysis** | `string` | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [Optional] [Defaults to `undefined`] |
| **topic** | `string` | Only sentiments tagged with this topic (case-insensitive) | [Optional] [Defaults to `undefined`] |
| **query** | `string` | Only sentiments whose answer or prompt text contains this text | [Optional] [Defaults to `undefined`] |
| **brand** | `string` | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [Optional] [Defaults to `undefined`] |
| **sort** | `mentions`, `name`, `positive`, `negative`, `neutral`, `net_score` | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [Optional] [Defaults to `&#39;mentions&#39;`] [Enum: mentions, name, positive, negative, neutral, net_score] |
| **sortDir** | `desc`, `asc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: desc, asc] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**SentimentTopicsResponse**](SentimentTopicsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated topic rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSentimentCategories

> listSentimentCategories(projectId, output)

List sentiment categories (Growth plan or above)

Sentiment metric keys + labels + colors. For records, use /sentiments. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```ts
import {
  Configuration,
  SentimentsApi,
} from '@llmpulse/sdk';
import type { ListSentimentCategoriesRequest } from '@llmpulse/sdk';

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
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListSentimentCategoriesRequest;

  try {
    const data = await api.listSentimentCategories(body);
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
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

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
| **200** | Sentiment buckets |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSentimentRecords

> SentimentsResponse listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records (Growth plan or above)

Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

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
    // string | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative (optional)
    analysis: analysis_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | 'naver_ai_tab' | 'qwen' | 'doubao' | Filter by one AI model. Here an unknown value, or a model the API key\'s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
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
| **analysis** | `string` | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai`, `naver_ai_tab`, `qwen`, `doubao` | Filter by one AI model. Here an unknown value, or a model the API key\&#39;s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

[**SentimentsResponse**](SentimentsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated sentiments |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

