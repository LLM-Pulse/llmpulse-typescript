# SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getSearchConsoleAiVisibilityGaps**](SearchConsoleApi.md#getsearchconsoleaivisibilitygaps) | **GET** /search_console/ai_visibility_gaps | Search Console queries vs AI tracking (Growth+) |
| [**getSearchConsoleBrandSplit**](SearchConsoleApi.md#getsearchconsolebrandsplit) | **GET** /search_console/brand_split | Search Console branded vs non-branded split (Growth+) |
| [**getSearchConsoleCannibalization**](SearchConsoleApi.md#getsearchconsolecannibalization) | **GET** /search_console/cannibalization | Search Console keyword cannibalization (Growth+) |
| [**getSearchConsoleDecay**](SearchConsoleApi.md#getsearchconsoledecay) | **GET** /search_console/decay | Search Console content decay (Growth+) |
| [**getSearchConsoleOpportunities**](SearchConsoleApi.md#getsearchconsoleopportunities) | **GET** /search_console/opportunities | Search Console ranking opportunities (Growth+) |
| [**getSearchConsolePages**](SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**getSearchConsoleQueries**](SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**getSearchConsoleRows**](SearchConsoleApi.md#getsearchconsolerows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+) |
| [**getSearchConsoleSummary**](SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**getSearchConsoleTimeseries**](SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |
| [**listSearchConsoleProperties**](SearchConsoleApi.md#listsearchconsoleproperties) | **GET** /search_console/properties | List Search Console properties (Growth+) |



## getSearchConsoleAiVisibilityGaps

> SearchConsoleAiVisibilityGapsResponse getSearchConsoleAiVisibilityGaps(projectId, property, range, from, to, minImpressions, unmatchedOnly, page, perPage, output, searchType, filters, dataState, aggregationType)

Search Console queries vs AI tracking (Growth+)

The property\&#39;s queries with at least min_impressions impressions, most impressions first, each matched against the project\&#39;s prompts. A query matches a prompt with the same text (match_type prompt) or, failing that, a prompt whose AI answers ran that same search in the window (match_type fan_out). Both matches are exact and deliberately conservative: the same text once both are lowercased, accents and similar letters folded the way AI answers are matched for brand mentions, spacing squeezed and leading or trailing punctuation dropped (best crm for agencies matches Best CRM for agencies?, but not What is the best CRM for agencies, and matches a search only when the answer ran exactly that search). When two prompts share a text (other countries or languages), the oldest is the match. When several prompts ran a search, the match is the one with the most answers running it, then the oldest. Searches are read from the successful answers of the project\&#39;s live prompts in the window, over the account\&#39;s enabled models; only some models report them, mainly ChatGPT, and they are usually much longer than a Google query, so fan_out matches are few. A matched query carries its prompt_id, match_type, responses (the prompt\&#39;s AI answers in the same window, over the account\&#39;s enabled models) and brand_visibility, the percent of those answers that mention the brand (null before any answer), as /metrics/prompt_summary computes it. unmatched_only&#x3D;true lists only the queries no prompt matches: search demand the AI tracking does not cover yet, the strongest candidates to add as prompts. Rows with a prompt and a low brand_visibility are queries people search for where AI answers rarely mention the brand; how low is low is the caller\&#39;s choice. matched_count counts the qualifying queries a prompt matches, either way. A team member also needs read access to the Overview, which holds prompt-level Brand Visibility, or gets ERR_INSUFFICIENT_PERMISSION; one without read access to Query Fan-Out gets only the text matches. Reads Google\&#39;s top 25,000 queries per property (truncated: true when reached) and excludes anonymized queries. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleAiVisibilityGapsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // number | Smallest impressions a query needs. (optional)
    minImpressions: 56,
    // boolean | List only the queries no prompt of the project matches (true or false). (optional)
    unmatchedOnly: true,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
  } satisfies GetSearchConsoleAiVisibilityGapsRequest;

  try {
    const data = await api.getSearchConsoleAiVisibilityGaps(body);
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
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **minImpressions** | `number` | Smallest impressions a query needs. | [Optional] [Defaults to `100`] |
| **unmatchedOnly** | `boolean` | List only the queries no prompt of the project matches (true or false). | [Optional] [Defaults to `false`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleAiVisibilityGapsResponse**](SearchConsoleAiVisibilityGapsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Queries matched against the project\&#39;s prompts |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleBrandSplit

> SearchConsoleBrandSplitResponse getSearchConsoleBrandSplit(projectId, property, range, from, to, searchType, filters, dataState, aggregationType)

Search Console branded vs non-branded split (Growth+)

Splits the property\&#39;s impressions and clicks into branded queries, which contain one of the project\&#39;s brand terms as a whole word, case-insensitively (brand_terms: its brand name, matching names, app names and domain, each also matched with its accents folded and with either apostrophe, so Nestlé also matches nestle and L’Oréal matches l\&#39;oreal), and non-branded ones, next to the unfiltered totals. Google applies the split itself as a regular-expression query filter, so it covers every query Google counts, not only the 25,000 rows one read lists. Use it to see how much search traffic comes from people who already know the brand and how much from discovery searches, and how each side evolves across date ranges. Google leaves anonymized queries out of any query filter, so unclassified holds the impressions and clicks neither side counts. Returns ERR_INVALID_PARAM when the brand terms are too long for one Google filter (4,096 characters, Google\&#39;s documented limit), and ERR_SEARCH_CONSOLE_UPSTREAM (503) if Google refuses the filter built from them; our team is alerted in that case. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleBrandSplitRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
  } satisfies GetSearchConsoleBrandSplitRequest;

  try {
    const data = await api.getSearchConsoleBrandSplit(body);
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
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleBrandSplitResponse**](SearchConsoleBrandSplitResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Branded and non-branded totals |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleCannibalization

> SearchConsoleCannibalizationResponse getSearchConsoleCannibalization(projectId, property, range, from, to, minImpressions, minShare, page, perPage, output, searchType, filters, dataState, aggregationType)

Search Console keyword cannibalization (Growth+)

Queries with at least min_impressions impressions for which two or more pages each take at least min_share (default 0.1) of the query\&#39;s impressions, most impressions first, each with its competing pages (share, impressions, clicks, ctr, position). Use it to find the keywords several of the site\&#39;s pages fight over, and decide which pages to merge, redirect or differentiate. Google counts page-by-query impressions per page, so a query\&#39;s impressions here can exceed its property-wide figure. Reads Google\&#39;s top 25,000 page-query rows per property (truncated: true when reached). With output&#x3D;flat or csv, each competing page is its own row, with its URL in page_url. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. Jump links of one page (/post/#section) are merged into its base URL before the shares are computed, so a page never competes with itself; the query string stays.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleCannibalizationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // number | Smallest impressions a query needs. (optional)
    minImpressions: 56,
    // number | Smallest fraction (0.01 to 0.5) of the query\'s impressions a page needs to count as competing. (optional)
    minShare: 8.14,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
  } satisfies GetSearchConsoleCannibalizationRequest;

  try {
    const data = await api.getSearchConsoleCannibalization(body);
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
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **minImpressions** | `number` | Smallest impressions a query needs. | [Optional] [Defaults to `100`] |
| **minShare** | `number` | Smallest fraction (0.01 to 0.5) of the query\&#39;s impressions a page needs to count as competing. | [Optional] [Defaults to `0.1`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleCannibalizationResponse**](SearchConsoleCannibalizationResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competing pages per query |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleDecay

> SearchConsoleDecayResponse getSearchConsoleDecay(projectId, property, range, from, to, dimension, minClicks, page, perPage, output, searchType, filters, dataState, aggregationType)

Search Console content decay (Growth+)

Pages (or queries, with dimension&#x3D;query) that had at least min_clicks clicks in the window just before the requested one (previous_from to previous_to, the same length) and lost clicks since, biggest loss first, with clicks, impressions and average position in both windows. Use it to find the pages losing traffic and to tell lost rankings (a worse position) from lost demand (fewer impressions at a stable position). The requested window ends at compared_through, the last day Google has published when that is before to, so days Google has not filled in yet never read as a loss. Both windows must fit in Google\&#39;s 487-day retention, or the request returns ERR_INVALID_PARAM. Reads Google\&#39;s top 25,000 rows per window and property (truncated: true when reached); when the requested window reaches that cap, a page or query missing from it is left out rather than read as a loss. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. With dimension&#x3D;page, a URL with a fragment (/post/#section) is merged into its base URL in both windows; the query string stays.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleDecayRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'page' | 'query' | Compare pages or queries. (optional)
    dimension: dimension_example,
    // number | Smallest clicks in the previous window. (optional)
    minClicks: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
  } satisfies GetSearchConsoleDecayRequest;

  try {
    const data = await api.getSearchConsoleDecay(body);
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
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **dimension** | `page`, `query` | Compare pages or queries. | [Optional] [Defaults to `&#39;page&#39;`] [Enum: page, query] |
| **minClicks** | `number` | Smallest clicks in the previous window. | [Optional] [Defaults to `10`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleDecayResponse**](SearchConsoleDecayResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Pages or queries losing clicks |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleOpportunities

> SearchConsoleOpportunitiesResponse getSearchConsoleOpportunities(projectId, property, range, from, to, minImpressions, minPosition, maxPosition, page, perPage, output, searchType, filters, dataState, aggregationType)

Search Console ranking opportunities (Growth+)

Queries whose average position is between min_position and max_position (default 4 to 20) with at least min_impressions impressions, ranked by potential_clicks: the clicks a move into the top 3 would add at top_ctr, the CTR the property\&#39;s own queries averaging position 3 or better get in the same window. Use it to find the queries where a small ranking gain would add the most traffic. No outside CTR curve is used: with no top-3 query in the window, top_ctr and potential_clicks are null. Reads Google\&#39;s top 25,000 queries per property (truncated: true when reached) and excludes anonymized queries. Requires a connected Search Console property (Growth+). Live reads only: under stored reads it returns ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleOpportunitiesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // number | Smallest impressions a query needs. (optional)
    minImpressions: 56,
    // number | Best average position to include. (optional)
    minPosition: 8.14,
    // number | Worst average position to include; at least min_position. (optional)
    maxPosition: 8.14,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
  } satisfies GetSearchConsoleOpportunitiesRequest;

  try {
    const data = await api.getSearchConsoleOpportunities(body);
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
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **minImpressions** | `number` | Smallest impressions a query needs. | [Optional] [Defaults to `100`] |
| **minPosition** | `number` | Best average position to include. | [Optional] [Defaults to `4`] |
| **maxPosition** | `number` | Worst average position to include; at least min_position. | [Optional] [Defaults to `20`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |

### Return type

[**SearchConsoleOpportunitiesResponse**](SearchConsoleOpportunitiesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Ranking opportunities |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsolePages

> SearchConsoleListResponse getSearchConsolePages(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType, property)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, and start_row reads the next block. Page rows are counted per page rather than per property, so they can differ from the totals. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM. A page URL that Google reports with a fragment (/post/#section, a table-of-contents jump link) is merged into its base URL (impressions and clicks summed, position impression-weighted, ctr recomputed) before ranking and paging; the query string stays.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsolePagesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'impressions' | 'clicks' | 'ctr' | 'position' (optional)
    sort: sort_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // number | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. (optional)
    startRow: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
  } satisfies GetSearchConsolePagesRequest;

  try {
    const data = await api.getSearchConsolePages(body);
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
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **sort** | `impressions`, `clicks`, `ctr`, `position` |  | [Optional] [Defaults to `&#39;impressions&#39;`] [Enum: impressions, clicks, ctr, position] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **startRow** | `number` | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [Optional] [Defaults to `0`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top pages |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleQueries

> SearchConsoleListResponse getSearchConsoleQueries(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType, property)

Top Search Console queries (Growth+)

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, so the rows add up to less than the totals, and start_row reads the next block. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleQueriesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'impressions' | 'clicks' | 'ctr' | 'position' (optional)
    sort: sort_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // number | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. (optional)
    startRow: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
  } satisfies GetSearchConsoleQueriesRequest;

  try {
    const data = await api.getSearchConsoleQueries(body);
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
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **sort** | `impressions`, `clicks`, `ctr`, `position` |  | [Optional] [Defaults to `&#39;impressions&#39;`] [Enum: impressions, clicks, ctr, position] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **startRow** | `number` | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [Optional] [Defaults to `0`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchConsoleListResponse**](SearchConsoleListResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top queries |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleRows

> SearchConsoleRowsResponse getSearchConsoleRows(projectId, dimensions, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType, property)

Search Console rows by several dimensions (Growth+)

Google Search Console rows grouped by 1 to 3 dimensions (date, country, device, page, query, searchAppearance, property) over a date range, each row carrying its dimension values as fields plus impressions, clicks, ctr (0..1) and position, ranked by impressions, clicks, ctr or position, paginated. Google ranks rows by clicks and returns at most 25,000 per request (truncated: true when reached); start_row moves that window. Query rows exclude anonymized queries, so rows add up to less than the summary totals. Requires a connected Search Console property (Growth+) and live reads: stored reads return ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access and ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A combination Google refuses comes back as ERR_INVALID_PARAM with its reason. Page values are merged the same way: a URL with a fragment (/post/#section) counts in its base URL\&#39;s row, with impressions and clicks summed and position impression-weighted; the query string stays.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleRowsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance, property. Each becomes a field of every row; country and device values are lowercase. property is the Search Console property the row comes from (see the property parameter).
    dimensions: page,query,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'impressions' | 'clicks' | 'ctr' | 'position' (optional)
    sort: sort_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // number | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. (optional)
    startRow: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
  } satisfies GetSearchConsoleRowsRequest;

  try {
    const data = await api.getSearchConsoleRows(body);
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
| **dimensions** | `string` | Comma-separated dimensions to group by, 1 to 3 of date, country, device, page, query, searchAppearance, property. Each becomes a field of every row; country and device values are lowercase. property is the Search Console property the row comes from (see the property parameter). | [Defaults to `undefined`] |
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **sort** | `impressions`, `clicks`, `ctr`, `position` |  | [Optional] [Defaults to `&#39;impressions&#39;`] [Enum: impressions, clicks, ctr, position] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **startRow** | `number` | Google ranks rows by clicks and returns at most 25,000 per request. start_row moves that window down the ranking (e.g. 25000 for the next block); sort and pagination apply within the window. | [Optional] [Defaults to `0`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchConsoleRowsResponse**](SearchConsoleRowsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console rows |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleSummary

> SearchConsoleSummaryResponse getSearchConsoleSummary(projectId, range, from, to, dimension, limit, searchType, filters, dataState, aggregationType, property)

Search Console summary (Growth+)

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension&#x3D;country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit, or dimension&#x3D;property for one row per property read (with a property list or property&#x3D;all). With filters and no dimension, totals are the complete figure Google reports for that filter. Breakdown rows are capped by limit and by Google\&#39;s 25,000-row maximum; breakdown_truncated: true means rows were left out. Query rows exclude anonymized queries, and page and searchAppearance rows are counted per page rather than per property, so breakdown rows can differ from the totals. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A page URL that Google reports with a fragment (/post/#section, a table-of-contents jump link) is merged into its base URL before the breakdown is ranked and limited; the query string stays.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleSummaryRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'country' | 'device' | 'page' | 'query' | 'searchAppearance' | 'property' | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. property gives one row per property read (see the property parameter). (optional)
    dimension: dimension_example,
    // number | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows. (optional)
    limit: 56,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
  } satisfies GetSearchConsoleSummaryRequest;

  try {
    const data = await api.getSearchConsoleSummary(body);
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
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **dimension** | `country`, `device`, `page`, `query`, `searchAppearance`, `property` | Optional breakdown aggregated over the range. country and device are lowercased; page and query keep the casing Google returns, because a page URL is case sensitive. property gives one row per property read (see the property parameter). | [Optional] [Defaults to `undefined`] [Enum: country, device, page, query, searchAppearance, property] |
| **limit** | `number` | Maximum breakdown rows, sorted by impressions descending. Default and maximum 1000. Use /search_console/queries or /search_console/pages to page through up to 25,000 rows. | [Optional] [Defaults to `undefined`] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchConsoleSummaryResponse**](SearchConsoleSummaryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console summary |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSearchConsoleTimeseries

> SearchConsoleTimeseriesResponse getSearchConsoleTimeseries(projectId, range, from, to, granularity, output, searchType, filters, dataState, aggregationType, property)

Search Console time series (Growth+)

Google Search Console series (impressions, clicks, ctr, position) bucketed by day, week or month, property-wide unless filters narrows it. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { GetSearchConsoleTimeseriesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back, today included (alternative to from/to). At most 487, Google\'s retention. (optional)
    range: 56,
    // Date | Start date (YYYY-MM-DD). Defaults to 30 days ago. (optional)
    from: 2013-10-20,
    // Date | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. (optional)
    to: 2013-10-20,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
    // 'web' | 'image' | 'video' | 'news' | 'discover' | 'googleNews' | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. (optional)
    searchType: searchType_example,
    // string | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters=[{\"dimension\":\"page\",\"operator\":\"contains\",\"expression\":\"/blog/\"}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]=page&filters[][operator]=contains&filters[][expression]=/blog/ is also accepted. (optional)
    filters: [{"dimension":"page","operator":"contains","expression":"/blog/"}],
    // 'final' | 'all' | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. (optional)
    dataState: dataState_example,
    // 'auto' | 'byPage' | 'byProperty' | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. (optional)
    aggregationType: aggregationType_example,
    // string | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. (optional)
    property: all,
  } satisfies GetSearchConsoleTimeseriesRequest;

  try {
    const data = await api.getSearchConsoleTimeseries(body);
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
| **range** | `number` | Number of days to look back, today included (alternative to from/to). At most 487, Google\&#39;s retention. | [Optional] [Defaults to `undefined`] |
| **from** | `Date` | Start date (YYYY-MM-DD). Defaults to 30 days ago. | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End date (YYYY-MM-DD), inclusive. Defaults to today. Google publishes data with a 2-3 day lag, so data_through in the response says how far it reaches. | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |
| **searchType** | `web`, `image`, `video`, `news`, `discover`, `googleNews` | Which search surface to measure. Defaults to web. discover and googleNews carry no query dimension, so Google rejects /search_console/queries for them. | [Optional] [Defaults to `&#39;web&#39;`] [Enum: web, image, video, news, discover, googleNews] |
| **filters** | `string` | Narrow the query; every entry must match (AND). Send the whole list as one JSON value: filters&#x3D;[{\&quot;dimension\&quot;:\&quot;page\&quot;,\&quot;operator\&quot;:\&quot;contains\&quot;,\&quot;expression\&quot;:\&quot;/blog/\&quot;}] (URL-encoded). An array of objects has no query-parameter form a generated client can produce, so the string is what the official SDKs send; see the SearchConsoleFilters schema for the shape it encodes. includingRegex and excludingRegex take RE2 syntax. At most 10 entries, expression at most 500 characters. The bracket form filters[][dimension]&#x3D;page&amp;filters[][operator]&#x3D;contains&amp;filters[][expression]&#x3D;/blog/ is also accepted. | [Optional] [Defaults to `undefined`] |
| **dataState** | `final`, `all` | final (default) counts only rows Google has finalized. all also counts the most recent days, which are still being filled in and will change. | [Optional] [Defaults to `&#39;final&#39;`] [Enum: final, all] |
| **aggregationType** | `auto`, `byPage`, `byProperty` | How Google counts impressions. auto (default) is what Search Console shows (by page when page is grouped or filtered, else by property). Google rejects byProperty with a page dimension or filter. | [Optional] [Defaults to `&#39;auto&#39;`] [Enum: auto, byPage, byProperty] |
| **property** | `string` | Which Search Console properties to read; /search_console/properties lists them. Omit it for the primary property, or pass one property id (e.g. sc-domain:example.com) to read that one; both answer with property. A comma-separated list of ids, or all, combines several and answers with properties, excluded_properties and property_errors instead: excluded_properties are left out because another selected property already counts them (a URL-prefix property under a domain property), so no click is counted twice; property_errors are properties Google refused, left out of the figures and also named in the X-Search-Console-Property-Errors header. When Google refuses every property, the request fails as a single-property read would. | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchConsoleTimeseriesResponse**](SearchConsoleTimeseriesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console time series |  -  |
| **401** | Authentication failed |  -  |
| **403** | Plan below Growth (ERR_PLAN_REQUIRED), or Google revoked the project\&#39;s Search Console access (ERR_SEARCH_CONSOLE_ACCESS_REVOKED): reconnect the property |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage |  * Retry-After - Seconds to wait before retrying <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSearchConsoleProperties

> SearchConsolePropertiesResponse listSearchConsoleProperties(projectId, output)

List Search Console properties (Growth+)

The Google Search Console properties connected to the project, up to max_properties, from one or more Google accounts, primary first. Each id is a value the property parameter of the other /search_console endpoints accepts: omit it for the primary property, pass one id, or a comma-separated list or all to combine several. type is domain (sc-domain:example.com, which counts every subdomain and protocol) or url_prefix. status reconnect_required means Google refused the stored access; reconnect the property in Preferences &gt; Project Settings &gt; Connections. An empty data list means the project has no Search Console connection. Requires the Growth plan or above.

### Example

```ts
import {
  Configuration,
  SearchConsoleApi,
} from '@llmpulse/sdk';
import type { ListSearchConsolePropertiesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SearchConsoleApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListSearchConsolePropertiesRequest;

  try {
    const data = await api.listSearchConsoleProperties(body);
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

[**SearchConsolePropertiesResponse**](SearchConsolePropertiesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search Console properties |  -  |
| **401** | Authentication failed |  -  |
| **403** | Access forbidden |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

