# StoreIntegrationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**acceptCatalogPromptSuggestions**](StoreIntegrationsApi.md#acceptcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions |
| [**createCatalogPromptSuggestions**](StoreIntegrationsApi.md#createcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products |
| [**getStoreConnection**](StoreIntegrationsApi.md#getstoreconnection) | **GET** /store_connection | Match a store to a project |
| [**listAiOrders**](StoreIntegrationsApi.md#listaiorders) | **GET** /ai_orders | Read AI-referred store orders |
| [**listCatalogPromptSuggestions**](StoreIntegrationsApi.md#listcatalogpromptsuggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions |
| [**rejectCatalogPromptSuggestions**](StoreIntegrationsApi.md#rejectcatalogpromptsuggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions |
| [**replaceAiOrders**](StoreIntegrationsApi.md#replaceaiorders) | **PUT** /ai_orders | Replace AI-referred store orders for a window |



## acceptCatalogPromptSuggestions

> CatalogPromptSuggestionsAcceptResponse acceptCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)

Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { AcceptCatalogPromptSuggestionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // CatalogPromptSuggestionIdsRequest
    catalogPromptSuggestionIdsRequest: ...,
  } satisfies AcceptCatalogPromptSuggestionsRequest;

  try {
    const data = await api.acceptCatalogPromptSuggestions(body);
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
| **catalogPromptSuggestionIdsRequest** | [CatalogPromptSuggestionIdsRequest](CatalogPromptSuggestionIdsRequest.md) |  | |

### Return type

[**CatalogPromptSuggestionsAcceptResponse**](CatalogPromptSuggestionsAcceptResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Accepted and skipped suggestions |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createCatalogPromptSuggestions

> CatalogPromptSuggestionsCreateResponse createCatalogPromptSuggestions(catalogPromptSuggestionsCreateRequest)

Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project\&#39;s Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { CreateCatalogPromptSuggestionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // CatalogPromptSuggestionsCreateRequest
    catalogPromptSuggestionsCreateRequest: ...,
  } satisfies CreateCatalogPromptSuggestionsRequest;

  try {
    const data = await api.createCatalogPromptSuggestions(body);
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
| **catalogPromptSuggestionsCreateRequest** | [CatalogPromptSuggestionsCreateRequest](CatalogPromptSuggestionsCreateRequest.md) |  | |

### Return type

[**CatalogPromptSuggestionsCreateResponse**](CatalogPromptSuggestionsCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The suggestions saved for these products |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **502** | The AI generation failed; retry the request |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getStoreConnection

> StoreConnectionResponse getStoreConnection(platform, domain)

Match a store to a project

Tells a store app whether the API key\&#39;s account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { GetStoreConnectionRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // 'shopify' | Store platform
    platform: platform_example,
    // string | Store domain, with or without scheme, e.g. acme-store.com
    domain: domain_example,
  } satisfies GetStoreConnectionRequest;

  try {
    const data = await api.getStoreConnection(body);
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
| **platform** | `shopify` | Store platform | [Defaults to `undefined`] [Enum: shopify] |
| **domain** | `string` | Store domain, with or without scheme, e.g. acme-store.com | [Defaults to `undefined`] |

### Return type

[**StoreConnectionResponse**](StoreConnectionResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Eligibility, the matching project and the candidates |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAiOrders

> AiOrdersResponse listAiOrders(projectId, platform, from, to)

Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { ListAiOrdersRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'shopify' | Store platform (optional)
    platform: platform_example,
    // Date | First day (YYYY-MM-DD). Defaults to 89 days before to (optional)
    from: 2013-10-20,
    // Date | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days (optional)
    to: 2013-10-20,
  } satisfies ListAiOrdersRequest;

  try {
    const data = await api.listAiOrders(body);
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
| **platform** | `shopify` | Store platform | [Optional] [Defaults to `&#39;shopify&#39;`] [Enum: shopify] |
| **from** | `Date` | First day (YYYY-MM-DD). Defaults to 89 days before to | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days | [Optional] [Defaults to `undefined`] |

### Return type

[**AiOrdersResponse**](AiOrdersResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Totals, per-assistant rows and the daily series |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCatalogPromptSuggestions

> CatalogPromptSuggestionsResponse listCatalogPromptSuggestions(projectId, status, productExternalId, page, perPage)

List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { ListCatalogPromptSuggestionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'pending' | 'accepted' | 'rejected' | Only suggestions in this status (optional)
    status: status_example,
    // string | Only suggestions for this store product id (optional)
    productExternalId: productExternalId_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListCatalogPromptSuggestionsRequest;

  try {
    const data = await api.listCatalogPromptSuggestions(body);
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
| **status** | `pending`, `accepted`, `rejected` | Only suggestions in this status | [Optional] [Defaults to `undefined`] [Enum: pending, accepted, rejected] |
| **productExternalId** | `string` | Only suggestions for this store product id | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `50`] |

### Return type

[**CatalogPromptSuggestionsResponse**](CatalogPromptSuggestionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## rejectCatalogPromptSuggestions

> CatalogPromptSuggestionsRejectResponse rejectCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)

Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { RejectCatalogPromptSuggestionsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // CatalogPromptSuggestionIdsRequest
    catalogPromptSuggestionIdsRequest: ...,
  } satisfies RejectCatalogPromptSuggestionsRequest;

  try {
    const data = await api.rejectCatalogPromptSuggestions(body);
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
| **catalogPromptSuggestionIdsRequest** | [CatalogPromptSuggestionIdsRequest](CatalogPromptSuggestionIdsRequest.md) |  | |

### Return type

[**CatalogPromptSuggestionsRejectResponse**](CatalogPromptSuggestionsRejectResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | How many suggestions were rejected |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## replaceAiOrders

> AiOrdersUpdateResponse replaceAiOrders(aiOrdersUpdateRequest)

Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order\&#39;s first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```ts
import {
  Configuration,
  StoreIntegrationsApi,
} from '@llmpulse/sdk';
import type { ReplaceAiOrdersRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new StoreIntegrationsApi(config);

  const body = {
    // AiOrdersUpdateRequest
    aiOrdersUpdateRequest: ...,
  } satisfies ReplaceAiOrdersRequest;

  try {
    const data = await api.replaceAiOrders(body);
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
| **aiOrdersUpdateRequest** | [AiOrdersUpdateRequest](AiOrdersUpdateRequest.md) |  | |

### Return type

[**AiOrdersUpdateResponse**](AiOrdersUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Rows stored and entries ignored |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

