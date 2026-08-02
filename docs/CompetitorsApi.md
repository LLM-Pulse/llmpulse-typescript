# CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCompetitor**](CompetitorsApi.md#createcompetitoroperation) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor**](CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**updateCompetitor**](CompetitorsApi.md#updatecompetitoroperation) | **PATCH** /competitors/{id} | Update a competitor |



## createCompetitor

> createCompetitor(createCompetitorRequest)

Add a competitor

Adds a competitor (brand name + domain) to a project. Honours the per-plan max competitors cap. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { CreateCompetitorOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // CreateCompetitorRequest
    createCompetitorRequest: ...,
  } satisfies CreateCompetitorOperationRequest;

  try {
    const data = await api.createCompetitor(body);
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
| **createCompetitorRequest** | [CreateCompetitorRequest](CreateCompetitorRequest.md) |  | |

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
| **201** | Created |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteCompetitor

> deleteCompetitor(projectId, id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; its tracked data is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { DeleteCompetitorRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies DeleteCompetitorRequest;

  try {
    const data = await api.deleteCompetitor(body);
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
| **200** | Deleted |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateCompetitor

> updateCompetitor(id, updateCompetitorRequest)

Update a competitor

Updates brand_name, matching_names (full replacement list; the brand name is always included automatically) and/or color. The domain is immutable after creation. Name changes re-run mention/citation matching in the background: the competitor shows processing&#x3D;true for a few minutes and further edits are rejected meanwhile. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { UpdateCompetitorOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // number
    id: 56,
    // UpdateCompetitorRequest
    updateCompetitorRequest: ...,
  } satisfies UpdateCompetitorOperationRequest;

  try {
    const data = await api.updateCompetitor(body);
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
| **id** | `number` |  | [Defaults to `undefined`] |
| **updateCompetitorRequest** | [UpdateCompetitorRequest](UpdateCompetitorRequest.md) |  | |

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
| **200** | Updated |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

