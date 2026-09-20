# OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listOwnedMedia**](OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listRedditCitations**](OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content |



## listOwnedMedia

> listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List owned-media citations

Which owned-media content AI answers cite, by platform. &#x60;provider&#x60; is required. Each row carries a &#x60;yours&#x60; flag so you can compare your own presence against everyone else cited on the same platform. view&#x3D;own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. Requires the Growth plan or above.

### Example

```ts
import {
  Configuration,
  OwnedMediaCommunitiesApi,
} from '@llmpulse/sdk';
import type { ListOwnedMediaRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OwnedMediaCommunitiesApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'youtube' | 'instagram' | 'facebook' | 'tiktok' | 'linkedin' | 'mobile_apps' | The platform to report on
    provider: provider_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'videos' | 'channels' | 'posts' | 'profiles' | 'own_citations' | 'apps' | Row shape; the allowed set depends on provider (optional)
    view: view_example,
    // 'google_play' | 'app_store' | provider=mobile_apps only (optional)
    store: store_example,
    // boolean | Return only rows belonging to the account\'s own connected profile (optional)
    owned: true,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | 'naver_ai' | 'baidu_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs (optional)
    collectionId: ...,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
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
  } satisfies ListOwnedMediaRequest;

  try {
    const data = await api.listOwnedMedia(body);
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
| **provider** | `youtube`, `instagram`, `facebook`, `tiktok`, `linkedin`, `mobile_apps` | The platform to report on | [Defaults to `undefined`] [Enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **view** | `videos`, `channels`, `posts`, `profiles`, `own_citations`, `apps` | Row shape; the allowed set depends on provider | [Optional] [Defaults to `undefined`] [Enum: videos, channels, posts, profiles, own_citations, apps] |
| **store** | `google_play`, `app_store` | provider&#x3D;mobile_apps only | [Optional] [Defaults to `&#39;google_play&#39;`] [Enum: google_play, app_store] |
| **owned** | `boolean` | Return only rows belonging to the account\&#39;s own connected profile | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus`, `naver_ai`, `baidu_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [](.md) | One collection/tag ID or a comma-separated list of IDs | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
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
| **200** | Paginated owned-media rows |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRedditCitations

> listRedditCitations(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view&#x3D;subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view&#x3D;authors returns one row per author; view&#x3D;threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. Requires the Growth plan or above.

### Example

```ts
import {
  Configuration,
  OwnedMediaCommunitiesApi,
} from '@llmpulse/sdk';
import type { ListRedditCitationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OwnedMediaCommunitiesApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'subreddits' | 'authors' | 'threads' (optional)
    view: view_example,
    // string | Filter to one subreddit (name without the r/ prefix) (optional)
    subreddit: subreddit_example,
    // string | Filter to one Reddit author (optional)
    author: author_example,
    // 'open' | 'archived' | view=threads only (optional)
    status: status_example,
    // boolean | Return only subreddits/authors the account has claimed as its own (optional)
    owned: true,
    // string | Filter to citations whose scraped Reddit content mentions a brand: \'brand\' for the tracked brand, or a competitor id. Reads the page content, not the AI answer. (optional)
    brand: brand_example,
    // 'citations' | 'subreddit' | 'unique_authors' | 'positive_pct' | 'negative_pct' | 'author' | 'avg_position' | 'upvotes' | 'comments' | 'sentiment' | Sort field; the allowed set depends on view (optional)
    order: order_example,
    // 'asc' | 'desc' (optional)
    direction: direction_example,
    // 'chatgpt' | 'perplexity' | 'gemini' | 'ai_overview' | 'ai_mode' | 'copilot' | 'claude' | 'grok' | 'deepseek' | 'meta_ai' | 'amazon_rufus' | 'naver_ai' | 'baidu_ai' | Filter by AI model. Models the API key\'s user has not enabled are silently dropped. (optional)
    model: model_example,
    // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs (optional)
    collectionId: ...,
    // string | One ISO country code or a comma-separated list (e.g. US,GB,DE) (optional)
    countryCode: countryCode_example,
    // string | One ISO language code or a comma-separated list (e.g. en,es,de) (optional)
    languageCode: languageCode_example,
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
  } satisfies ListRedditCitationsRequest;

  try {
    const data = await api.listRedditCitations(body);
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
| **view** | `subreddits`, `authors`, `threads` |  | [Optional] [Defaults to `&#39;subreddits&#39;`] [Enum: subreddits, authors, threads] |
| **subreddit** | `string` | Filter to one subreddit (name without the r/ prefix) | [Optional] [Defaults to `undefined`] |
| **author** | `string` | Filter to one Reddit author | [Optional] [Defaults to `undefined`] |
| **status** | `open`, `archived` | view&#x3D;threads only | [Optional] [Defaults to `undefined`] [Enum: open, archived] |
| **owned** | `boolean` | Return only subreddits/authors the account has claimed as its own | [Optional] [Defaults to `undefined`] |
| **brand** | `string` | Filter to citations whose scraped Reddit content mentions a brand: \&#39;brand\&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [Optional] [Defaults to `undefined`] |
| **order** | `citations`, `subreddit`, `unique_authors`, `positive_pct`, `negative_pct`, `author`, `avg_position`, `upvotes`, `comments`, `sentiment` | Sort field; the allowed set depends on view | [Optional] [Defaults to `undefined`] [Enum: citations, subreddit, unique_authors, positive_pct, negative_pct, author, avg_position, upvotes, comments, sentiment] |
| **direction** | `asc`, `desc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus`, `naver_ai`, `baidu_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [](.md) | One collection/tag ID or a comma-separated list of IDs | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
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
| **200** | Paginated Reddit rows |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

