# OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getOwnedMediaProfiles**](OwnedMediaCommunitiesApi.md#getownedmediaprofiles) | **GET** /projects/{id}/owned_media | Get a project\&#39;s owned-media profiles |
| [**getOwnedMediaSummary**](OwnedMediaCommunitiesApi.md#getownedmediasummary) | **GET** /dimensions/owned_media/summary | Get an owned-media summary |
| [**listOwnedMedia**](OwnedMediaCommunitiesApi.md#listownedmedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listOwnedMediaCitingPrompts**](OwnedMediaCommunitiesApi.md#listownedmediacitingprompts) | **GET** /dimensions/owned_media/citing_prompts | List the answers citing an owned-media item |
| [**listRedditCitations**](OwnedMediaCommunitiesApi.md#listredditcitations) | **GET** /dimensions/reddit | List cited Reddit content |
| [**updateOwnedMediaProfiles**](OwnedMediaCommunitiesApi.md#updateownedmediaprofilesoperation) | **PATCH** /projects/{id}/owned_media | Update a project\&#39;s owned-media profiles |



## getOwnedMediaProfiles

> OwnedMediaProfilesResponse getOwnedMediaProfiles(id)

Get a project\&#39;s owned-media profiles

The profiles whose citations count as yours in the Owned Media and YouTube Intelligence reports, as Project Settings &gt; Owned Media shows them. platforms holds one entry per platform with whether it is connected, how many extra profiles it accepts and its profiles: the main one, the extra ones, and on Reddit the claimed subreddits and usernames, each with its URL, handle, store (for apps), name, avatar and the state of the scrape that reads them. settings holds the current value of every field PATCH accepts, ready to edit and send back. Requires the Growth plan or above.

### Example

```ts
import {
  Configuration,
  OwnedMediaCommunitiesApi,
} from '@llmpulse/sdk';
import type { GetOwnedMediaProfilesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OwnedMediaCommunitiesApi(config);

  const body = {
    // number | Project ID
    id: 56,
  } satisfies GetOwnedMediaProfilesRequest;

  try {
    const data = await api.getOwnedMediaProfiles(body);
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
| **id** | `number` | Project ID | [Defaults to `undefined`] |

### Return type

[**OwnedMediaProfilesResponse**](OwnedMediaProfilesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Profiles per platform and the editable settings |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED, and a team member whose permissions do not grant Owned Media ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOwnedMediaSummary

> OwnedMediaSummaryResponse getOwnedMediaSummary(projectId, provider, model, collectionId, countryCode, languageCode, brandKind, range, from, to)

Get an owned-media summary

The numbers behind one Owned Media tab. kpis gives the platform citations (total), yours (your profiles and their content), your_profile and your_content apart, and share_pct; previous gives the same KPIs for the period of the same length that ends just before from, and changes the difference (percent for counts, percentage points for share_pct, null when there is nothing to compare). weekly is the citations per week, yours against everyone else. by_model and by_country split every citation of the platform; content_types (reel, post, tv, pulse, or regular, shorts and live on YouTube) and age_buckets cover posts and videos. provider&#x3D;mobile_apps adds stores, the per-store totals, and has no content type or age; provider&#x3D;overview returns platforms, one rollup per platform the caller can read, and no breakdowns. A team member also needs the YouTube Intelligence permission for provider&#x3D;youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Example

```ts
import {
  Configuration,
  OwnedMediaCommunitiesApi,
} from '@llmpulse/sdk';
import type { GetOwnedMediaSummaryRequest } from '@llmpulse/sdk';

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
    // 'youtube' | 'instagram' | 'facebook' | 'tiktok' | 'linkedin' | 'mobile_apps' | 'overview' | The platform to summarize, or overview for every platform at once
    provider: provider_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
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
  } satisfies GetOwnedMediaSummaryRequest;

  try {
    const data = await api.getOwnedMediaSummary(body);
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
| **provider** | `youtube`, `instagram`, `facebook`, `tiktok`, `linkedin`, `mobile_apps`, `overview` | The platform to summarize, or overview for every platform at once | [Defaults to `undefined`] [Enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps, overview] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |

### Return type

[**OwnedMediaSummaryResponse**](OwnedMediaSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The KPI cards, comparison, weekly series and breakdowns |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED. A team member whose permissions do not grant Owned Media (or YouTube Intelligence for provider&#x3D;youtube) answers ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOwnedMedia

> OwnedMediaListResponse listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List owned-media citations

Which owned-media content AI answers cite, by platform. &#x60;provider&#x60; is required. Each row carries a &#x60;yours&#x60; flag so you can compare your own presence against everyone else cited on the same platform. Video, post, channel and profile rows also carry their image (thumbnail_url or avatar_url, our cached copy where one exists), their average position in the answers and, on YouTube, the video id, the channel handle and URL, and the channel key that /dimensions/owned_media/citing_prompts accepts. view&#x3D;own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. A team member also needs the YouTube Intelligence permission for provider&#x3D;youtube. Requires the Growth plan or above.

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
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
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
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**OwnedMediaListResponse**](OwnedMediaListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated owned-media rows |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED. A team member whose permissions do not grant Owned Media (or YouTube Intelligence for provider&#x3D;youtube) answers ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listOwnedMediaCitingPrompts

> OwnedMediaCitingPromptsResponse listOwnedMediaCitingPrompts(projectId, provider, page, perPage, url, profile, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List the answers citing an owned-media item

The drill-down behind one row of an Owned Media or YouTube Intelligence table. Pass exactly one of url (a post or video URL, any variant of it) or profile (a handle with or without @, a profile or channel URL, or the channel key the YouTube channels rows return). item describes it (title, image, owner, whether it is yours and its stats), citation_count and prompt_count count its citations in the window, and data lists the citing answers newest first, each with its prompt, answer id, model, country, language, execution date, a plain-text excerpt and its link in the app. It shows prompt and answer text, so a team member also needs the Prompts permission, and YouTube Intelligence for provider&#x3D;youtube. Defaults to the last 30 days. Requires the Growth plan or above.

### Example

```ts
import {
  Configuration,
  OwnedMediaCommunitiesApi,
} from '@llmpulse/sdk';
import type { ListOwnedMediaCitingPromptsRequest } from '@llmpulse/sdk';

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
    // 'youtube' | 'instagram' | 'facebook' | 'tiktok' | 'linkedin' | The platform the item belongs to
    provider: provider_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // string | A post or video URL, or a profile or channel URL. Exclusive with profile (optional)
    url: url_example,
    // string | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url (optional)
    profile: profile_example,
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
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
  } satisfies ListOwnedMediaCitingPromptsRequest;

  try {
    const data = await api.listOwnedMediaCitingPrompts(body);
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
| **provider** | `youtube`, `instagram`, `facebook`, `tiktok`, `linkedin` | The platform the item belongs to | [Defaults to `undefined`] [Enum: youtube, instagram, facebook, tiktok, linkedin] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **url** | `string` | A post or video URL, or a profile or channel URL. Exclusive with profile | [Optional] [Defaults to `undefined`] |
| **profile** | `string` | A handle (with or without @), a profile or channel URL, or a YouTube channel key (handle:..., channel:... or name:...). Exclusive with url | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
| **countryCode** | `string` | One ISO country code or a comma-separated list (e.g. US,GB,DE) | [Optional] [Defaults to `undefined`] |
| **languageCode** | `string` | One ISO language code or a comma-separated list (e.g. en,es,de) | [Optional] [Defaults to `undefined`] |
| **brandKind** | `brand`, `brand_other`, `non_brand` | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [Optional] [Defaults to `undefined`] [Enum: brand, brand_other, non_brand] |
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**OwnedMediaCitingPromptsResponse**](OwnedMediaCitingPromptsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The item and a page of the answers that cited it |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED. A team member whose permissions do not grant Owned Media and Prompts (and YouTube Intelligence for provider&#x3D;youtube) answers ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
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
    // 'chatgpt' | 'perplexity' | 'ai_mode' | 'ai_overview' | 'gemini' | 'copilot' | 'amazon_rufus' | 'claude' | 'grok' | 'deepseek' | 'naver_ai' | 'baidu_ai' | 'meta_ai' | Filter by one AI model. It must be a model enabled for the API key\'s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. (optional)
    model: model_example,
    // string | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. (optional)
    collectionId: 12,34,
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
| **model** | `chatgpt`, `perplexity`, `ai_mode`, `ai_overview`, `gemini`, `copilot`, `amazon_rufus`, `claude`, `grok`, `deepseek`, `naver_ai`, `baidu_ai`, `meta_ai` | Filter by one AI model. It must be a model enabled for the API key\&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | `string` | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [Optional] [Defaults to `undefined`] |
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


## updateOwnedMediaProfiles

> OwnedMediaProfilesUpdateResponse updateOwnedMediaProfiles(id, updateOwnedMediaProfilesRequest)

Update a project\&#39;s owned-media profiles

Sets the profiles whose citations count as yours, like Project Settings &gt; Owned Media. Send only the fields to change: a URL field takes a URL, or an empty string or null to clear it, and every list REPLACES the stored one ([] clears it). URLs are normalized like the app (a profile URL is stored in its canonical form, a Google Play package name becomes its listing URL), and anything the app would refuse (a URL from another platform, an extra profile equal to the main one, more than 10 extra profiles, a malformed subreddit) is rejected with ERR_INVALID_PARAM and nothing is applied. A new main or extra profile is scraped in the background for its name and avatar, listed in profile_scrapes_queued. The response is the GET payload after the change. A team member needs the Owned Media create permission, YouTube Intelligence create to change the YouTube channel, and Projects update to change the extra profile or Reddit lists. Requires the Growth plan or above and a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  OwnedMediaCommunitiesApi,
} from '@llmpulse/sdk';
import type { UpdateOwnedMediaProfilesOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OwnedMediaCommunitiesApi(config);

  const body = {
    // number | Project ID
    id: 56,
    // UpdateOwnedMediaProfilesRequest
    updateOwnedMediaProfilesRequest: ...,
  } satisfies UpdateOwnedMediaProfilesOperationRequest;

  try {
    const data = await api.updateOwnedMediaProfiles(body);
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
| **id** | `number` | Project ID | [Defaults to `undefined`] |
| **updateOwnedMediaProfilesRequest** | [UpdateOwnedMediaProfilesRequest](UpdateOwnedMediaProfilesRequest.md) |  | |

### Return type

[**OwnedMediaProfilesUpdateResponse**](OwnedMediaProfilesUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The profiles after the change |  -  |
| **403** | A plan below Growth answers ERR_PLAN_REQUIRED, a read-only key ERR_INSUFFICIENT_SCOPE, and a team member without the Owned Media create permission (or YouTube Intelligence create for the YouTube channel) ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

