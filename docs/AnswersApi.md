# AnswersApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAnswer**](AnswersApi.md#getanswer) | **GET** /answers/{id} | Get one AI response |
| [**listAnswers**](AnswersApi.md#listanswers) | **GET** /answers | List AI responses |



## getAnswer

> AnswerDetails getAnswer(projectId, id, includeSourcePageDetails)

Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass &#x60;include_source_page_details&#x3D;true&#x60; to nest page-cache metadata under each source.

### Example

```ts
import {
  Configuration,
  AnswersApi,
} from '@llmpulse/sdk';
import type { GetAnswerRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AnswersApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
    // boolean (optional)
    includeSourcePageDetails: true,
  } satisfies GetAnswerRequest;

  try {
    const data = await api.getAnswer(body);
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
| **includeSourcePageDetails** | `boolean` |  | [Optional] [Defaults to `false`] |

### Return type

[**AnswerDetails**](AnswerDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Answer details |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAnswers

> listAnswers(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query, noResult)

List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass &#x60;query&#x60; for case-insensitive full-text search inside response texts: &#x60;total&#x60; becomes the exact count of matching responses and each item returns &#x60;snippet&#x60; + &#x60;match_count&#x60; instead of &#x60;response&#x60;/&#x60;response_truncated&#x60;.

### Example

```ts
import {
  Configuration,
  AnswersApi,
} from '@llmpulse/sdk';
import type { ListAnswersRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AnswersApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | 'naver_ai' | 'baidu_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // 'mentions_you' | 'not_mentions_you' | 'mentions_competitor' | 'not_mentions_competitor' | 'you_and_competitor' | 'competitor_not_you' | 'you_not_competitor' | 'no_brands' | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with \'competitors\' to narrow the competitor side to specific rivals; on a negative cell that reads \'none of these\'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value \'competitors_only\' is still accepted as an alias of competitor_not_you. (optional)
    mentionFilter: mentionFilter_example,
    // 'cites_you' | 'not_cites_you' | 'cites_competitor' | 'not_cites_competitor' | 'you_and_competitor' | 'competitor_not_you' | 'you_not_competitor' | 'cites_no_brands' | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). (optional)
    citationFilter: citationFilter_example,
    // string | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) (optional)
    competitors: competitors_example,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // string | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. (optional)
    query: query_example,
    // boolean | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false = only real answers, true = only sentinels, omit = both. Every item carries its own no_result flag. (optional)
    noResult: true,
  } satisfies ListAnswersRequest;

  try {
    const data = await api.listAnswers(body);
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
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus`, `naver_ai`, `baidu_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **mentionFilter** | `mentions_you`, `not_mentions_you`, `mentions_competitor`, `not_mentions_competitor`, `you_and_competitor`, `competitor_not_you`, `you_not_competitor`, `no_brands` | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with \&#39;competitors\&#39; to narrow the competitor side to specific rivals; on a negative cell that reads \&#39;none of these\&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value \&#39;competitors_only\&#39; is still accepted as an alias of competitor_not_you. | [Optional] [Defaults to `undefined`] [Enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **citationFilter** | `cites_you`, `not_cites_you`, `cites_competitor`, `not_cites_competitor`, `you_and_competitor`, `competitor_not_you`, `you_not_competitor`, `cites_no_brands` | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [Optional] [Defaults to `undefined`] [Enum: cites_you, not_cites_you, cites_competitor, not_cites_competitor, you_and_competitor, competitor_not_you, you_not_competitor, cites_no_brands] |
| **competitors** | `string` | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **query** | `string` | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. | [Optional] [Defaults to `undefined`] |
| **noResult** | `boolean` | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false &#x3D; only real answers, true &#x3D; only sentinels, omit &#x3D; both. Every item carries its own no_result flag. | [Optional] [Defaults to `undefined`] |

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
| **200** | Paginated answers |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

