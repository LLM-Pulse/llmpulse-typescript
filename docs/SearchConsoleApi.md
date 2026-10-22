# SearchConsoleApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getSearchConsolePages**](SearchConsoleApi.md#getsearchconsolepages) | **GET** /search_console/pages | Top Search Console pages (Growth+) |
| [**getSearchConsoleQueries**](SearchConsoleApi.md#getsearchconsolequeries) | **GET** /search_console/queries | Top Search Console queries (Growth+) |
| [**getSearchConsoleRows**](SearchConsoleApi.md#getsearchconsolerows) | **GET** /search_console/rows | Search Console rows by several dimensions (Growth+) |
| [**getSearchConsoleSummary**](SearchConsoleApi.md#getsearchconsolesummary) | **GET** /search_console/summary | Search Console summary (Growth+) |
| [**getSearchConsoleTimeseries**](SearchConsoleApi.md#getsearchconsoletimeseries) | **GET** /search_console/timeseries | Search Console time series (Growth+) |
| [**listSearchConsoleProperties**](SearchConsoleApi.md#listsearchconsoleproperties) | **GET** /search_console/properties | List Search Console properties (Growth+) |



## getSearchConsolePages

> SearchConsoleListResponse getSearchConsolePages(projectId, range, from, to, sort, page, perPage, startRow, output, searchType, filters, dataState, aggregationType, property)

Top Search Console pages (Growth+)

Top Google Search Console landing pages over a date range, ranked by impressions, clicks, ctr or position, paginated. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, and start_row reads the next block. Page rows are counted per page rather than per property, so they can differ from the totals. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

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

Top Google Search Console search queries over a date range, ranked by impressions, clicks, ctr or position, paginated. Excludes anonymized queries; for headline totals use /search_console/summary. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. total counts the rows returned by one Google request, up to 25,000; truncated: true means that limit was reached, so the rows add up to less than the totals, and start_row reads the next block. Sorting and pagination apply to the available set. Stored reads cannot answer this endpoint and return ERR_INVALID_PARAM.

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

Google Search Console rows grouped by 1 to 3 dimensions (date, country, device, page, query, searchAppearance, property) over a date range, each row carrying its dimension values as fields plus impressions, clicks, ctr (0..1) and position, ranked by impressions, clicks, ctr or position, paginated. Google ranks rows by clicks and returns at most 25,000 per request (truncated: true when reached); start_row moves that window. Query rows exclude anonymized queries, so rows add up to less than the summary totals. Requires a connected Search Console property (Growth+) and live reads: stored reads return ERR_INVALID_PARAM. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access and ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying. A combination Google refuses comes back as ERR_INVALID_PARAM with its reason.

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

Google Search Console headline totals (impressions, clicks, ctr as a 0..1 fraction, average position) for the project over a date range. Pass dimension&#x3D;country, device, page, query or searchAppearance to also receive the breakdown aggregated over the range, capped by limit, or dimension&#x3D;property for one row per property read (with a property list or property&#x3D;all). With filters and no dimension, totals are the complete figure Google reports for that filter. Breakdown rows are capped by limit and by Google\&#39;s 25,000-row maximum; breakdown_truncated: true means rows were left out. Query rows exclude anonymized queries, and page and searchAppearance rows are counted per page rather than per property, so breakdown rows can differ from the totals. Requires the project to have a connected Search Console property and the Growth plan or above; otherwise returns ERR_SEARCH_CONSOLE_NOT_CONNECTED or ERR_PLAN_REQUIRED. X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

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

Google Search Console series (impressions, clicks, ctr, position) bucketed by day, week or month, property-wide unless filters narrows it. Requires a connected Search Console property (Growth+). X-Search-Console-Backend identifies stored or live reads. Stored reads use synced data without contacting Google. Live reads return ERR_SEARCH_CONSOLE_ACCESS_REVOKED (403) for revoked Google access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. They return ERR_SEARCH_CONSOLE_UPSTREAM (503) when Google Search Console is unavailable or over quota; wait for the number of seconds in Retry-After before retrying.

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

The Google Search Console properties connected to the project, up to max_properties, from one or more Google accounts, primary first. Each id is a value the property parameter of the other /search_console endpoints accepts: omit it for the primary property, pass one id, or a comma-separated list or all to combine several. type is domain (sc-domain:example.com, which counts every subdomain and protocol) or url_prefix. status reconnect_required means Google refused the stored access; reconnect the property in Preferences &gt; Project Settings &gt; Data Connections. An empty data list means the project has no Search Console connection. Requires the Growth plan or above.

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

