# RecommendationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getRecommendation**](RecommendationsApi.md#getrecommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**launchRecommendations**](RecommendationsApi.md#launchrecommendationsoperation) | **POST** /recommendations | Launch a recommendations generation |
| [**listRecommendations**](RecommendationsApi.md#listrecommendations) | **GET** /recommendations | List recommendation runs |



## getRecommendation

> getRecommendation(projectId, id, itemStatus, resolveSourceRefs)

Get recommendation run with items

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@llmpulse/sdk';
import type { GetRecommendationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
    // 'active' | 'completed' | 'archived' (optional)
    itemStatus: itemStatus_example,
    // boolean (optional)
    resolveSourceRefs: true,
  } satisfies GetRecommendationRequest;

  try {
    const data = await api.getRecommendation(body);
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
| **itemStatus** | `active`, `completed`, `archived` |  | [Optional] [Defaults to `undefined`] [Enum: active, completed, archived] |
| **resolveSourceRefs** | `boolean` |  | [Optional] [Defaults to `true`] |

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
| **200** | Recommendation detail with items |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## launchRecommendations

> launchRecommendations(launchRecommendationsRequest)

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@llmpulse/sdk';
import type { LaunchRecommendationsOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // LaunchRecommendationsRequest
    launchRecommendationsRequest: ...,
  } satisfies LaunchRecommendationsOperationRequest;

  try {
    const data = await api.launchRecommendations(body);
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
| **launchRecommendationsRequest** | [LaunchRecommendationsRequest](LaunchRecommendationsRequest.md) |  | |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Generation launched (status pending) |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRecommendations

> RecommendationsResponse listRecommendations(projectId, recommendationType, status, page, perPage)

List recommendation runs

### Example

```ts
import {
  Configuration,
  RecommendationsApi,
} from '@llmpulse/sdk';
import type { ListRecommendationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RecommendationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'ai_visibility' | 'social_community' | 'brand_building' | 'sentiment_reputation' (optional)
    recommendationType: recommendationType_example,
    // 'pending' | 'processing' | 'completed' | 'failed' (optional)
    status: status_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListRecommendationsRequest;

  try {
    const data = await api.listRecommendations(body);
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
| **recommendationType** | `ai_visibility`, `social_community`, `brand_building`, `sentiment_reputation` |  | [Optional] [Defaults to `undefined`] [Enum: ai_visibility, social_community, brand_building, sentiment_reputation] |
| **status** | `pending`, `processing`, `completed`, `failed` |  | [Optional] [Defaults to `undefined`] [Enum: pending, processing, completed, failed] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

[**RecommendationsResponse**](RecommendationsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated recommendations |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

