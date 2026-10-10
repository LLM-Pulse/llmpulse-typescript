# AIAgentTrafficApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAgentTraffic**](AIAgentTrafficApi.md#getagenttraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**getAiTraffic**](AIAgentTrafficApi.md#getaitraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**getWebAnalyticsSchema**](AIAgentTrafficApi.md#getwebanalyticsschema) | **GET** /web_analytics/schema | Web analytics query format (Growth+) |
| [**listAgentBots**](AIAgentTrafficApi.md#listagentbots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |
| [**queryWebAnalytics**](AIAgentTrafficApi.md#querywebanalyticsoperation) | **POST** /web_analytics/query | Live web analytics query (Growth+) |



## getAgentTraffic

> AgentTrafficResponse getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity)

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project\&#39;s origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```ts
import {
  Configuration,
  AIAgentTrafficApi,
} from '@llmpulse/sdk';
import type { GetAgentTrafficRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIAgentTrafficApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // string | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) (optional)
    bot: bot_example,
    // string | Filter by company (e.g. openai, anthropic, google) (optional)
    company: company_example,
    // 'bot' | 'company' (optional)
    groupBy: groupBy_example,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
  } satisfies GetAgentTrafficRequest;

  try {
    const data = await api.getAgentTraffic(body);
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
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **bot** | `string` | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [Optional] [Defaults to `undefined`] |
| **company** | `string` | Filter by company (e.g. openai, anthropic, google) | [Optional] [Defaults to `undefined`] |
| **groupBy** | `bot`, `company` |  | [Optional] [Defaults to `&#39;bot&#39;`] [Enum: bot, company] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |

### Return type

[**AgentTrafficResponse**](AgentTrafficResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Agent traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAiTraffic

> getAiTraffic(projectId, range, from, to, source, granularity)

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible, Matomo or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```ts
import {
  Configuration,
  AIAgentTrafficApi,
} from '@llmpulse/sdk';
import type { GetAiTrafficRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIAgentTrafficApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Number of days to look back (alternative to from/to) (optional)
    range: 56,
    // Date (optional)
    from: 2013-10-20T19:20:30+01:00,
    // Date | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. (optional)
    to: 2013-10-20T19:20:30+01:00,
    // string | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) (optional)
    source: source_example,
    // 'day' | 'week' | 'month' (optional)
    granularity: granularity_example,
  } satisfies GetAiTrafficRequest;

  try {
    const data = await api.getAiTraffic(body);
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
| **range** | `number` | Number of days to look back (alternative to from/to) | [Optional] [Defaults to `undefined`] |
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [Optional] [Defaults to `undefined`] |
| **source** | `string` | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [Optional] [Defaults to `undefined`] |
| **granularity** | `day`, `week`, `month` |  | [Optional] [Defaults to `undefined`] [Enum: day, week, month] |

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
| **200** | AI referral traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWebAnalyticsSchema

> WebAnalyticsSchemaResponse getWebAnalyticsSchema(projectId)

Web analytics query format (Growth+)

How to query the web analytics provider connected to the project, live: the provider, the property every query runs on, the native query format it accepts, the allowed top-level fields, the rules the bridge enforces (the connected property is always used, only reads run, row limits), a worked example and, where the provider offers it, its live field list. Cached for an hour. Supported providers: Google Analytics 4, Adobe Analytics or Customer Journey Analytics, Matomo, PostHog, Plausible and Piano, connected on the AI Traffic page. Requires the Growth plan or above; otherwise ERR_PLAN_REQUIRED. Without a connected provider returns ERR_WEB_ANALYTICS_NOT_CONNECTED (404); a provider that refuses the stored credentials returns ERR_WEB_ANALYTICS_ACCESS_REVOKED (403); an unavailable provider, an exhausted provider quota, more than 20 uncached queries a minute or too many running at once for the project returns ERR_WEB_ANALYTICS_UPSTREAM (503): wait for the number of seconds in Retry-After before retrying.

### Example

```ts
import {
  Configuration,
  AIAgentTrafficApi,
} from '@llmpulse/sdk';
import type { GetWebAnalyticsSchemaRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIAgentTrafficApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
  } satisfies GetWebAnalyticsSchemaRequest;

  try {
    const data = await api.getWebAnalyticsSchema(body);
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

### Return type

[**WebAnalyticsSchemaResponse**](WebAnalyticsSchemaResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Query format for the connected provider |  -  |
| **403** | Access forbidden |  -  |
| **404** | Resource not found |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds to wait before retrying: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAgentBots

> AgentBotsResponse listAgentBots(projectId, output)

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Example

```ts
import {
  Configuration,
  AIAgentTrafficApi,
} from '@llmpulse/sdk';
import type { ListAgentBotsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIAgentTrafficApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListAgentBotsRequest;

  try {
    const data = await api.listAgentBots(body);
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

[**AgentBotsResponse**](AgentBotsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bot catalog |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## queryWebAnalytics

> WebAnalyticsQueryResponse queryWebAnalytics(queryWebAnalyticsRequest)

Live web analytics query (Growth+)

Runs a read-only query, written in the connected provider\&#39;s native format, against the project\&#39;s property and returns columns and rows: a GA4 Data API runReport body, an Adobe Analytics or Customer Journey Analytics report request, Matomo Reporting API parameters (get methods only), PostHog HogQL, a Plausible Stats API v2 query or a Piano getData body. The connected property, site, report suite or project is always used and any property field in the query is ignored. Rows default to 100 and are capped at 5,000. Identical queries are answered from a 10-minute cache (cached: true). A query the provider rejects returns ERR_WEB_ANALYTICS_INVALID_QUERY (422) with the provider\&#39;s own validation message. Each uncached query spends the customer\&#39;s provider API quota. A read: no writable key is needed. Supported providers: Google Analytics 4, Adobe Analytics or Customer Journey Analytics, Matomo, PostHog, Plausible and Piano, connected on the AI Traffic page. Requires the Growth plan or above; otherwise ERR_PLAN_REQUIRED. Without a connected provider returns ERR_WEB_ANALYTICS_NOT_CONNECTED (404); a provider that refuses the stored credentials returns ERR_WEB_ANALYTICS_ACCESS_REVOKED (403); an unavailable provider, an exhausted provider quota, more than 20 uncached queries a minute or too many running at once for the project returns ERR_WEB_ANALYTICS_UPSTREAM (503): wait for the number of seconds in Retry-After before retrying.

### Example

```ts
import {
  Configuration,
  AIAgentTrafficApi,
} from '@llmpulse/sdk';
import type { QueryWebAnalyticsOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AIAgentTrafficApi(config);

  const body = {
    // QueryWebAnalyticsRequest
    queryWebAnalyticsRequest: {"project_id":123,"query":{"dateRanges":[{"startDate":"28daysAgo","endDate":"yesterday"}],"dimensions":[{"name":"sessionDefaultChannelGroup"}],"metrics":[{"name":"sessions"},{"name":"keyEvents"}],"limit":20}},
  } satisfies QueryWebAnalyticsOperationRequest;

  try {
    const data = await api.queryWebAnalytics(body);
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
| **queryWebAnalyticsRequest** | [QueryWebAnalyticsRequest](QueryWebAnalyticsRequest.md) |  | |

### Return type

[**WebAnalyticsQueryResponse**](WebAnalyticsQueryResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Query result as columns and rows |  -  |
| **403** | Access forbidden |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **503** | Upstream provider unavailable, retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds to wait before retrying: Google\&#39;s own value when it sent one, otherwise 900 after a quota error and 60 after an outage <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

