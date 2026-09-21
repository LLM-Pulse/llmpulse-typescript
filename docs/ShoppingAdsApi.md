# ShoppingAdsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listAds**](ShoppingAdsApi.md#listads) | **GET** /dimensions/ads | List AI ad placements |
| [**listShopping**](ShoppingAdsApi.md#listshopping) | **GET** /dimensions/shopping | List shopping results |



## listAds

> listAds(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List AI ad placements

Paid placements returned inside AI answers. view&#x3D;advertisers (default) returns one row per advertising domain with its placement count, prompt reach and average and best position; view&#x3D;ads returns the individual placements with title, snippet, position and the prompt that triggered them. Position 1 is the best slot, so a LOWER average position is better. Requires the Scale plan or above.

### Example

```ts
import {
  Configuration,
  ShoppingAdsApi,
} from '@llmpulse/sdk';
import type { ListAdsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ShoppingAdsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'advertisers' | 'ads' | Row shape: one per advertising domain, or one per placement (optional)
    view: view_example,
    // boolean | Return only placements identified as the tracked brand\'s own (view=ads) (optional)
    owned: true,
    // 'ads' | 'prompts' | 'avg_position' | 'domain' | 'recent' | 'oldest' | 'position' | Sort field; the allowed set depends on view (optional)
    order: order_example,
    // 'asc' | 'desc' | Sort direction for view=advertisers. Defaults to desc, except avg_position and domain which default to asc. (optional)
    direction: direction_example,
    // string | Case-insensitive substring filter on the ad title, domain or snippet (optional)
    query: query_example,
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
  } satisfies ListAdsRequest;

  try {
    const data = await api.listAds(body);
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
| **view** | `advertisers`, `ads` | Row shape: one per advertising domain, or one per placement | [Optional] [Defaults to `&#39;advertisers&#39;`] [Enum: advertisers, ads] |
| **owned** | `boolean` | Return only placements identified as the tracked brand\&#39;s own (view&#x3D;ads) | [Optional] [Defaults to `undefined`] |
| **order** | `ads`, `prompts`, `avg_position`, `domain`, `recent`, `oldest`, `position` | Sort field; the allowed set depends on view | [Optional] [Defaults to `undefined`] [Enum: ads, prompts, avg_position, domain, recent, oldest, position] |
| **direction** | `asc`, `desc` | Sort direction for view&#x3D;advertisers. Defaults to desc, except avg_position and domain which default to asc. | [Optional] [Defaults to `undefined`] [Enum: asc, desc] |
| **query** | `string` | Case-insensitive substring filter on the ad title, domain or snippet | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus`, `naver_ai`, `baidu_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
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
| **200** | Paginated ad rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listShopping

> listShopping(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List shopping results

Product cards returned inside AI answers. view&#x3D;products (default) returns one row per distinct product, merged across executions, with its appearance count, price range, rating and whether it is yours, plus a currency_count saying how many currencies it was priced in (above 1 means the row reports its highest-priced listing and min_price may be another currency); view&#x3D;merchants returns one row per selling merchant, with a currency field naming the money its price range and average are expressed in (providers price each market in its own currency, so a merchant that sells in more than one reports the currency most of its prices use). Every response also carries a totals block matching the KPI cards in the app, whose avg_price is computed inside the single currency named by avg_price_currency. Requires the Scale plan or above.

### Example

```ts
import {
  Configuration,
  ShoppingAdsApi,
} from '@llmpulse/sdk';
import type { ListShoppingRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ShoppingAdsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'products' | 'merchants' | Row shape: one per distinct product, or one per merchant (optional)
    view: view_example,
    // boolean | Return only products identified as the tracked brand\'s own. On view=merchants this narrows to the merchants selling those products; the totals block stays account-wide. (optional)
    owned: true,
    // 'appearances' | 'price' | 'rating' | 'title' | 'products' | 'avg_price' | 'avg_rating' | 'merchant' | Sort field; the allowed set depends on view (optional)
    order: order_example,
    // 'asc' | 'desc' (optional)
    direction: direction_example,
    // string | Case-insensitive substring filter on the product title (optional)
    query: query_example,
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
  } satisfies ListShoppingRequest;

  try {
    const data = await api.listShopping(body);
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
| **view** | `products`, `merchants` | Row shape: one per distinct product, or one per merchant | [Optional] [Defaults to `&#39;products&#39;`] [Enum: products, merchants] |
| **owned** | `boolean` | Return only products identified as the tracked brand\&#39;s own. On view&#x3D;merchants this narrows to the merchants selling those products; the totals block stays account-wide. | [Optional] [Defaults to `undefined`] |
| **order** | `appearances`, `price`, `rating`, `title`, `products`, `avg_price`, `avg_rating`, `merchant` | Sort field; the allowed set depends on view | [Optional] [Defaults to `undefined`] [Enum: appearances, price, rating, title, products, avg_price, avg_rating, merchant] |
| **direction** | `asc`, `desc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **query** | `string` | Case-insensitive substring filter on the product title | [Optional] [Defaults to `undefined`] |
| **model** | `chatgpt`, `perplexity`, `gemini`, `ai_overview`, `ai_mode`, `copilot`, `claude`, `grok`, `deepseek`, `meta_ai`, `amazon_rufus`, `naver_ai`, `baidu_ai` | Filter by AI model. Models the API key\&#39;s user has not enabled are silently dropped. | [Optional] [Defaults to `undefined`] [Enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
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
| **200** | Paginated shopping rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

