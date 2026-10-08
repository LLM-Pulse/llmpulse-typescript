# MentionsCitationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listAllCitations**](MentionsCitationsApi.md#listallcitations) | **GET** /dimensions/all_citations | List all citations (brand + competitor) |
| [**listAllMentions**](MentionsCitationsApi.md#listallmentions) | **GET** /dimensions/all_mentions | List all mentions (brand + competitor) |
| [**listCitations**](MentionsCitationsApi.md#listcitations) | **GET** /dimensions/citations | List brand citations |
| [**listCompetitorCitations**](MentionsCitationsApi.md#listcompetitorcitations) | **GET** /dimensions/competitor_citations | List competitor citations |
| [**listCompetitorMentions**](MentionsCitationsApi.md#listcompetitormentions) | **GET** /dimensions/competitor_mentions | List competitor mentions |
| [**listMentions**](MentionsCitationsApi.md#listmentions) | **GET** /dimensions/mentions | List brand mentions |



## listAllCitations

> listAllCitations(projectId, competitors, page, perPage, model, collectionId, prompt, from, to, output)

List all citations (brand + competitor)

Unified citations stream with an &#x60;actor_type&#x60; field on each record. Includes visible citations and background source references; background references use position 0, meaning no visible rank.

### Example

```ts
import {
  Configuration,
  MentionsCitationsApi,
} from '@llmpulse/sdk';
import type { ListAllCitationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MentionsCitationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListAllCitationsRequest;

  try {
    const data = await api.listAllCitations(body);
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
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

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
| **200** | Paginated citations with actor_type discriminator |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAllMentions

> listAllMentions(projectId, competitors, page, perPage, model, collectionId, prompt, from, to, output)

List all mentions (brand + competitor)

Unified mentions stream. Each record has an &#x60;actor_type&#x60; field (&#x60;project&#x60; or &#x60;competitor&#x60;) so the same payload covers both.

### Example

```ts
import {
  Configuration,
  MentionsCitationsApi,
} from '@llmpulse/sdk';
import type { ListAllMentionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MentionsCitationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListAllMentionsRequest;

  try {
    const data = await api.listAllMentions(body);
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
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

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
| **200** | Paginated mentions with actor_type discriminator |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCitations

> CitationsResponse listCitations(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, output)

List brand citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.

### Example

```ts
import {
  Configuration,
  MentionsCitationsApi,
} from '@llmpulse/sdk';
import type { ListCitationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MentionsCitationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
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
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListCitationsRequest;

  try {
    const data = await api.listCitations(body);
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
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**CitationsResponse**](CitationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated brand citations |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCompetitorCitations

> listCompetitorCitations(projectId, competitors, page, perPage, model, collectionId, prompt, from, to, output)

List competitor citations

Includes visible citations and background source references. Background references use position 0, meaning no visible rank.

### Example

```ts
import {
  Configuration,
  MentionsCitationsApi,
} from '@llmpulse/sdk';
import type { ListCompetitorCitationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MentionsCitationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListCompetitorCitationsRequest;

  try {
    const data = await api.listCompetitorCitations(body);
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
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

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
| **200** | Paginated competitor citations |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCompetitorMentions

> CompetitorMentionsResponse listCompetitorMentions(projectId, competitors, page, perPage, model, collectionId, prompt, from, to, output)

List competitor mentions

### Example

```ts
import {
  Configuration,
  MentionsCitationsApi,
} from '@llmpulse/sdk';
import type { ListCompetitorMentionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MentionsCitationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListCompetitorMentionsRequest;

  try {
    const data = await api.listCompetitorMentions(body);
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
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**CompetitorMentionsResponse**](CompetitorMentionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated competitor mentions |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listMentions

> MentionsResponse listMentions(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, output)

List brand mentions

### Example

```ts
import {
  Configuration,
  MentionsCitationsApi,
} from '@llmpulse/sdk';
import type { ListMentionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MentionsCitationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
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
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListMentionsRequest;

  try {
    const data = await api.listMentions(body);
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
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**MentionsResponse**](MentionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated brand mentions |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

