# PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**acceptSuggestedPrompts**](PromptsApi.md#acceptsuggestedprompts) | **POST** /suggested_prompts/accept | Accept suggested prompts |
| [**createPromptGeneration**](PromptsApi.md#createpromptgeneration) | **POST** /prompt_generations | Generate prompt suggestions |
| [**createPrompts**](PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt**](PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt |
| [**getPromptGeneration**](PromptsApi.md#getpromptgeneration) | **GET** /prompt_generations/{id} | Get a prompt generation run |
| [**importPrompts**](PromptsApi.md#importprompts) | **POST** /prompts/import | Import prompts |
| [**listPromptExecutions**](PromptsApi.md#listpromptexecutions) | **GET** /dimensions/prompt_executions | List prompt executions |
| [**listPrompts**](PromptsApi.md#listprompts) | **GET** /dimensions/prompts | List prompts |
| [**listQueryFanOuts**](PromptsApi.md#listqueryfanouts) | **GET** /dimensions/query_fan_outs | List query fan-out |
| [**listSuggestedPrompts**](PromptsApi.md#listsuggestedprompts) | **GET** /suggested_prompts | List suggested prompts |
| [**rejectSuggestedPrompts**](PromptsApi.md#rejectsuggestedprompts) | **POST** /suggested_prompts/reject | Reject suggested prompts |
| [**updatePrompt**](PromptsApi.md#updatepromptoperation) | **PATCH** /prompts/{id} | Edit a prompt\&#39;s categorization |



## acceptSuggestedPrompts

> SuggestedPromptsAcceptResponse acceptSuggestedPrompts(suggestedPromptsAcceptRequest)

Accept suggested prompts

Starts tracking up to 100 pending suggestions: each becomes a prompt in its own country and language, optionally put in one tag (tag_ids or tag_names; create_missing creates a missing name when the team member may create tags). Suggestions that are no longer pending come back in skipped. When the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { AcceptSuggestedPromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // SuggestedPromptsAcceptRequest
    suggestedPromptsAcceptRequest: ...,
  } satisfies AcceptSuggestedPromptsRequest;

  try {
    const data = await api.acceptSuggestedPrompts(body);
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
| **suggestedPromptsAcceptRequest** | [SuggestedPromptsAcceptRequest](SuggestedPromptsAcceptRequest.md) |  | |

### Return type

[**SuggestedPromptsAcceptResponse**](SuggestedPromptsAcceptResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Accepted and skipped suggestions |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createPromptGeneration

> PromptGenerationResponse createPromptGeneration(promptGenerationRequest)

Generate prompt suggestions

Starts a suggestion run with one of the generators behind the app\&#39;s Add prompts wizards and answers 202 with the run. website writes suggestions from the scraped website (80% non-brand, 20% brand; up to 100 per project, then ERR_LIMIT_REACHED), keyword from a keyword or the project profile (optionally around a competitor), topic from a topic, reddit from Reddit discussions of a topic or brand, paa from Google People Also Ask (up to 5 keywords, counted against the account\&#39;s 24-hour lookup allowance), reputational from brand reputation questions, translate from the project\&#39;s prompts of another locale, search_console from the connected property\&#39;s top queries of the last 28 days (Growth plan or above, ERR_PLAN_REQUIRED). The suggestions land in the Suggested prompts queue; poll GET /prompt_generations/{id}, then accept the ones you want with POST /suggested_prompts/accept. Nothing is tracked until accepted. The request is validated before the run starts, and refused with ERR_LIMIT_REACHED when the plan has no prompt slot left, or ERR_QUOTA_EXCEEDED after 60 runs in an hour (the per-user prompt suggestion allowance, shared with project setup). Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { CreatePromptGenerationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // PromptGenerationRequest
    promptGenerationRequest: ...,
  } satisfies CreatePromptGenerationRequest;

  try {
    const data = await api.createPromptGeneration(body);
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
| **promptGenerationRequest** | [PromptGenerationRequest](PromptGenerationRequest.md) |  | |

### Return type

[**PromptGenerationResponse**](PromptGenerationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The run, status processing |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createPrompts

> PromptsCreateResponse createPrompts(promptsCreateRequest)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. When the project does not run on the schedule (paused, or beyond the plan\&#39;s project limit) the prompts are still created, and the response says so with &#x60;tracked&#x60; false, &#x60;untracked_reason&#x60; and a &#x60;warning&#x60;. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { CreatePromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // PromptsCreateRequest
    promptsCreateRequest: ...,
  } satisfies CreatePromptsRequest;

  try {
    const data = await api.createPrompts(body);
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
| **promptsCreateRequest** | [PromptsCreateRequest](PromptsCreateRequest.md) |  | |

### Return type

[**PromptsCreateResponse**](PromptsCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deletePrompt

> deletePrompt(projectId, id)

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { DeletePromptRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies DeletePromptRequest;

  try {
    const data = await api.deletePrompt(body);
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
| **id** | `number` |  | [Defaults to `undefined`] |

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
| **200** | Deleted |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPromptGeneration

> PromptGenerationResponse getPromptGeneration(projectId, id)

Get a prompt generation run

Returns a run started with POST /prompt_generations: processing while the generator works, then completed with the suggestions it saved to the Suggested prompts queue, or failed with an error code and message. Poll every few seconds; most runs finish within a minute. Runs are kept for 24 hours, their suggestions stay in the queue.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { GetPromptGenerationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetPromptGenerationRequest;

  try {
    const data = await api.getPromptGeneration(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |

### Return type

[**PromptGenerationResponse**](PromptGenerationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The run |  -  |
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## importPrompts

> PromptsImportResponse importPrompts(promptsImportRequest)

Import prompts

The app\&#39;s CSV import as JSON: up to 500 rows, each with its own prompt, country_code, language_code (codes or names; both default to the project\&#39;s) and tags, created when missing. Duplicates are skipped and existing prompts still get the row\&#39;s tags. The prompt limits are checked before anything is written: when the new prompts would exceed the plan the call returns ERR_LIMIT_REACHED and imports nothing. A row is skipped and comes back in row_errors when its country or language is unknown, when it would give a prompt more than 50 tags (rows repeating a prompt add up) or when its tags would take the request past 500 new tags. For a team member without create access to Tags, a row that needs a tag that does not exist yet is skipped and comes back in row_errors. For a team member without update access to Prompts, a row matching a prompt that already existed adds no tags to it, and comes back in row_errors when it would have added one. Responds 201 when it created prompts, 200 otherwise. &#x60;tracked&#x60; false, with &#x60;untracked_reason&#x60; and a &#x60;warning&#x60;, means the project does not run on the schedule, so the imported prompts do not run until that changes. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { ImportPromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // PromptsImportRequest
    promptsImportRequest: ...,
  } satisfies ImportPromptsRequest;

  try {
    const data = await api.importPrompts(body);
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
| **promptsImportRequest** | [PromptsImportRequest](PromptsImportRequest.md) |  | |

### Return type

[**PromptsImportResponse**](PromptsImportResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Nothing new was created (every row was a duplicate) |  -  |
| **201** | Prompts imported |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPromptExecutions

> PromptExecutionsResponse listPromptExecutions(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, mentionFilter, citationFilter, competitors, output, promptType, brandKind)

List prompt executions

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { ListPromptExecutionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | 'naver_ai_tab' | 'qwen' | 'doubao' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
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
    // 'mentions_you' | 'not_mentions_you' | 'mentions_competitor' | 'not_mentions_competitor' | 'you_and_competitor' | 'competitor_not_you' | 'you_not_competitor' | 'no_brands' | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with \'competitors\' to narrow the competitor side to specific rivals; on a negative cell that reads \'none of these\'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value \'competitors_only\' is still accepted as an alias of competitor_not_you. (optional)
    mentionFilter: mentionFilter_example,
    // 'cites_you' | 'not_cites_you' | 'cites_competitor' | 'not_cites_competitor' | 'you_and_competitor' | 'competitor_not_you' | 'you_not_competitor' | 'cites_no_brands' | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). (optional)
    citationFilter: citationFilter_example,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // string | One prompt type or a comma-separated list: informational, navigational, commercial, transactional (optional)
    promptType: promptType_example,
    // 'brand' | 'brand_other' | 'non_brand' | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. (optional)
    brandKind: brandKind_example,
  } satisfies ListPromptExecutionsRequest;

  try {
    const data = await api.listPromptExecutions(body);
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
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai`, `naver_ai_tab`, `qwen`, `doubao` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **mentionFilter** | `mentions_you`, `not_mentions_you`, `mentions_competitor`, `not_mentions_competitor`, `you_and_competitor`, `competitor_not_you`, `you_not_competitor`, `no_brands` | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with \&#39;competitors\&#39; to narrow the competitor side to specific rivals; on a negative cell that reads \&#39;none of these\&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value \&#39;competitors_only\&#39; is still accepted as an alias of competitor_not_you. | [Optional] [Defaults to `undefined`] [Enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **citationFilter** | `cites_you`, `not_cites_you`, `cites_competitor`, `not_cites_competitor`, `you_and_competitor`, `competitor_not_you`, `you_not_competitor`, `cites_no_brands` | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [Optional] [Defaults to `undefined`] [Enum: cites_you, not_cites_you, cites_competitor, not_cites_competitor, you_and_competitor, competitor_not_you, you_not_competitor, cites_no_brands] |
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |

### Return type

[**PromptExecutionsResponse**](PromptExecutionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated executions. Every row carries app_url, the link that opens the answer in the app |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listPrompts

> PromptsResponse listPrompts(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, from, to, output)

List prompts

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { ListPromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | 'naver_ai_tab' | 'qwen' | 'doubao' | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key\'s user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation. (optional)
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
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListPromptsRequest;

  try {
    const data = await api.listPrompts(body);
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
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai`, `naver_ai_tab`, `qwen`, `doubao` | Keep only the prompts with at least one execution on this AI model, of any outcome and date (the prompts /dimensions/prompt_executions lists for the same model). Prompts have no model of their own, so a prompt with no execution on this model yet (a newly enabled model, or a locale the model does not cover) is left out. An unknown value, or a model the API key\&#39;s user has not enabled, returns 422 ERR_INVALID_PARAM. from and to still filter prompt creation. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**PromptsResponse**](PromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated prompts. Every row carries app_url, the link that opens the prompt in the app |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listQueryFanOuts

> listQueryFanOuts(projectId, page, perPage, view, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List query fan-out

The sub-queries a model actually issued when answering your tracked prompts. view&#x3D;query (default) returns one row per distinct sub-query with count and share of all occurrences; view&#x3D;prompt returns one row per prompt with how many distinct sub-queries it produced. Fan-out is reported mainly by ChatGPT, so an empty result usually means the models in scope do not expose it. The API returns the aggregation only: for a period-over-period delta, call it twice with explicit from/to.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { ListQueryFanOutsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'query' | 'prompt' | Row shape: one per distinct sub-query, or one per prompt (optional)
    view: view_example,
    // 'count' | 'share' | 'query_text' | 'total_count' | 'variations_count' | 'prompt_text' | Sort field; the allowed set depends on view (optional)
    order: order_example,
    // 'asc' | 'desc' (optional)
    direction: direction_example,
    // string | Case-insensitive substring filter on the sub-query text (optional)
    query: query_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | 'naver_ai_tab' | 'qwen' | 'doubao' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
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
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListQueryFanOutsRequest;

  try {
    const data = await api.listQueryFanOuts(body);
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
| **view** | `query`, `prompt` | Row shape: one per distinct sub-query, or one per prompt | [Optional] [Defaults to `&#39;query&#39;`] [Enum: query, prompt] |
| **order** | `count`, `share`, `query_text`, `total_count`, `variations_count`, `prompt_text` | Sort field; the allowed set depends on view | [Optional] [Defaults to `undefined`] [Enum: count, share, query_text, total_count, variations_count, prompt_text] |
| **direction** | `asc`, `desc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **query** | `string` | Case-insensitive substring filter on the sub-query text | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai`, `naver_ai_tab`, `qwen`, `doubao` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **promptType** | `string` | One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
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
| **200** | Paginated fan-out rows |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSuggestedPrompts

> SuggestedPromptsResponse listSuggestedPrompts(projectId, source, status, page, perPage)

List suggested prompts

Lists the project\&#39;s Suggested prompts queue, the same list the app\&#39;s Suggested Prompts tab shows, oldest first. It holds the suggestions of every generator (website, magic for keyword runs, topic, reddit, paa, reputational, translate, gsc for Search Console, catalog). Pending suggestions by default; status&#x3D;all also returns accepted (with the prompt they became) and rejected ones. Team members need create access to Prompts, like the app\&#39;s tab.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { ListSuggestedPromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'website' | 'magic' | 'paa' | 'topic' | 'reddit' | 'reputational' | 'gsc' | 'translate' | 'catalog' | Only suggestions from this generator (optional)
    source: source_example,
    // 'pending' | 'accepted' | 'rejected' | 'all' | Only suggestions in this status (optional)
    status: status_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListSuggestedPromptsRequest;

  try {
    const data = await api.listSuggestedPrompts(body);
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
| **source** | `website`, `magic`, `paa`, `topic`, `reddit`, `reputational`, `gsc`, `translate`, `catalog` | Only suggestions from this generator | [Optional] [Defaults to `undefined`] [Enum: website, magic, paa, topic, reddit, reputational, gsc, translate, catalog] |
| **status** | `pending`, `accepted`, `rejected`, `all` | Only suggestions in this status | [Optional] [Defaults to `&#39;pending&#39;`] [Enum: pending, accepted, rejected, all] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `50`] |

### Return type

[**SuggestedPromptsResponse**](SuggestedPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## rejectSuggestedPrompts

> SuggestedPromptsRejectResponse rejectSuggestedPrompts(suggestedPromptIdsRequest)

Reject suggested prompts

Marks up to 100 pending suggestions as rejected, so they leave the pending list; suggestions that are no longer pending stay as they are. Tracks and deletes nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { RejectSuggestedPromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // SuggestedPromptIdsRequest
    suggestedPromptIdsRequest: ...,
  } satisfies RejectSuggestedPromptsRequest;

  try {
    const data = await api.rejectSuggestedPrompts(body);
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
| **suggestedPromptIdsRequest** | [SuggestedPromptIdsRequest](SuggestedPromptIdsRequest.md) |  | |

### Return type

[**SuggestedPromptsRejectResponse**](SuggestedPromptsRejectResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The suggestions rejected |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updatePrompt

> PromptCategorizationResponse updatePrompt(id, updatePromptRequest)

Edit a prompt\&#39;s categorization

Manual categorization, exactly like editing the intent and brand badges on the prompt page: send &#x60;prompt_type&#x60;, &#x60;brand_kind&#x60; or both. The prompt is marked as manually categorized (&#x60;categorization_source&#x60; becomes &#x60;manual&#x60;), so automatic categorization no longer changes it; the prompt page can revert it to automatic. Any other field returns ERR_INVALID_PARAM. Not available from a white-label portal (ERR_INTEGRATION_UNAVAILABLE), where the page hides the editor. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on Prompts.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { UpdatePromptOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number
    id: 56,
    // UpdatePromptRequest
    updatePromptRequest: ...,
  } satisfies UpdatePromptOperationRequest;

  try {
    const data = await api.updatePrompt(body);
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
| **id** | `number` |  | [Defaults to `undefined`] |
| **updatePromptRequest** | [UpdatePromptRequest](UpdatePromptRequest.md) |  | |

### Return type

[**PromptCategorizationResponse**](PromptCategorizationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The prompt with its new categorization |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, a team member without the permission ERR_INSUFFICIENT_PERMISSION, and a request made on a white-label portal host, where the app does not offer this action, ERR_INTEGRATION_UNAVAILABLE, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

