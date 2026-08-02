# CitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getCitedUrlContent**](CitationIntelligenceApi.md#getcitedurlcontent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail**](CitationIntelligenceApi.md#getcitedurldetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain**](CitationIntelligenceApi.md#getmentionsbycitingdomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**listCitationGroups**](CitationIntelligenceApi.md#listcitationgroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences**](CitationIntelligenceApi.md#listcitedurloccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |



## getCitedUrlContent

> getCitedUrlContent(projectId, urlSha256)

Cited URL cached content

### Example

```ts
import {
  Configuration,
  CitationIntelligenceApi,
} from '@llmpulse/sdk';
import type { GetCitedUrlContentRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CitationIntelligenceApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | 64-character hex SHA-256 of the cited URL
    urlSha256: urlSha256_example,
  } satisfies GetCitedUrlContentRequest;

  try {
    const data = await api.getCitedUrlContent(body);
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
| **urlSha256** | `string` | 64-character hex SHA-256 of the cited URL | [Defaults to `undefined`] |

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
| **200** | Sanitized cached content + mention evidence |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getCitedUrlDetail

> getCitedUrlDetail(projectId, urlSha256)

Cited URL detail

### Example

```ts
import {
  Configuration,
  CitationIntelligenceApi,
} from '@llmpulse/sdk';
import type { GetCitedUrlDetailRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CitationIntelligenceApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | 64-character hex SHA-256 of the cited URL
    urlSha256: urlSha256_example,
  } satisfies GetCitedUrlDetailRequest;

  try {
    const data = await api.getCitedUrlDetail(body);
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
| **urlSha256** | `string` | 64-character hex SHA-256 of the cited URL | [Defaults to `undefined`] |

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
| **200** | URL-level intelligence |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMentionsByCitingDomain

> getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example

```ts
import {
  Configuration,
  CitationIntelligenceApi,
} from '@llmpulse/sdk';
import type { GetMentionsByCitingDomainRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CitationIntelligenceApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // Array<string> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
    domains: ...,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // number (optional)
    collectionId: 56,
    // string | ISO country code (e.g. US, GB, DE) (optional)
    countryCode: countryCode_example,
    // string | ISO language code (e.g. en, es, de) (optional)
    languageCode: languageCode_example,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date (optional)
    to: 2013-10-20T19:20:30+01:00,
  } satisfies GetMentionsByCitingDomainRequest;

  try {
    const data = await api.getMentionsByCitingDomain(body);
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
| **domains** | `Array<string>` | Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com | |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | `number` |  | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | ISO country code (e.g. US, GB, DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | ISO language code (e.g. en, es, de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` |  | [Optional] [Defaults to `undefined`] |

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
| **200** | Mention share per citing domain |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCitationGroups

> listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project\&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API.

### Example

```ts
import {
  Configuration,
  CitationIntelligenceApi,
} from '@llmpulse/sdk';
import type { ListCitationGroupsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CitationIntelligenceApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'url' | 'domain' | 'host' (optional)
    view: view_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'group_key' | 'total_responses' | 'total_citations' | 'citation_rate' | 'avg_citation_position' | 'first_seen_at' | 'last_seen_at' (optional)
    order: order_example,
    // 'asc' | 'desc' (optional)
    direction: direction_example,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // number (optional)
    collectionId: 56,
    // string | ISO country code (e.g. US, GB, DE) (optional)
    countryCode: countryCode_example,
    // string | ISO language code (e.g. en, es, de) (optional)
    languageCode: languageCode_example,
    // number | Filter by prompt ID (optional)
    prompt: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date (optional)
    to: 2013-10-20T19:20:30+01:00,
    // string (optional)
    query: query_example,
    // 'owned' | 'competitor' | 'third_party' | 'social_media' | 'own_domain' | 'ugc' | 'background' (optional)
    sourceType: sourceType_example,
    // 'negative' (optional)
    sentiment: sentiment_example,
    // 'mentioned' | 'gap' (optional)
    contentGap: contentGap_example,
  } satisfies ListCitationGroupsRequest;

  try {
    const data = await api.listCitationGroups(body);
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
| **view** | `url`, `domain`, `host` |  | [Optional] [Defaults to `&#39;url&#39;`] [Enum: url, domain, host] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **order** | `group_key`, `total_responses`, `total_citations`, `citation_rate`, `avg_citation_position`, `first_seen_at`, `last_seen_at` |  | [Optional] [Defaults to `undefined`] [Enum: group_key, total_responses, total_citations, citation_rate, avg_citation_position, first_seen_at, last_seen_at] |
| **direction** | `asc`, `desc` |  | [Optional] [Defaults to `undefined`] [Enum: asc, desc] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | `number` |  | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | ISO country code (e.g. US, GB, DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | ISO language code (e.g. en, es, de) | [Optional] [Defaults to `undefined`] |
| **prompt** | `number` | Filter by prompt ID | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **query** | `string` |  | [Optional] [Defaults to `undefined`] |
| **sourceType** | `owned`, `competitor`, `third_party`, `social_media`, `own_domain`, `ugc`, `background` |  | [Optional] [Defaults to `undefined`] [Enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | `negative` |  | [Optional] [Defaults to `undefined`] [Enum: negative] |
| **contentGap** | `mentioned`, `gap` |  | [Optional] [Defaults to `undefined`] [Enum: mentioned, gap] |

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
| **200** | Grouped citation intelligence |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCitedUrlOccurrences

> listCitedUrlOccurrences(projectId, urlSha256, page, perPage)

Cited URL occurrences

### Example

```ts
import {
  Configuration,
  CitationIntelligenceApi,
} from '@llmpulse/sdk';
import type { ListCitedUrlOccurrencesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CitationIntelligenceApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | 64-character hex SHA-256 of the cited URL
    urlSha256: urlSha256_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListCitedUrlOccurrencesRequest;

  try {
    const data = await api.listCitedUrlOccurrences(body);
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
| **urlSha256** | `string` | 64-character hex SHA-256 of the cited URL | [Defaults to `undefined`] |
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
| **200** | Paginated occurrences |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

