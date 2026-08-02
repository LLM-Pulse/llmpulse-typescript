# CollectionsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCollection**](CollectionsApi.md#createcollectionoperation) | **POST** /collections | Create a tag |
| [**deleteCollection**](CollectionsApi.md#deletecollection) | **DELETE** /collections/{id} | Delete a tag |
| [**updateCollection**](CollectionsApi.md#updatecollectionoperation) | **PATCH** /collections/{id} | Update a tag |



## createCollection

> createCollection(createCollectionRequest)

Create a tag

Creates a tag (Collection) in a project. Optional &#x60;prompt_ids&#x60; attaches existing prompts in the same call. Tag name must be unique per project (case-insensitive). Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CollectionsApi,
} from '@llmpulse/sdk';
import type { CreateCollectionOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CollectionsApi(config);

  const body = {
    // CreateCollectionRequest
    createCollectionRequest: ...,
  } satisfies CreateCollectionOperationRequest;

  try {
    const data = await api.createCollection(body);
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
| **createCollectionRequest** | [CreateCollectionRequest](CreateCollectionRequest.md) |  | |

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


## deleteCollection

> deleteCollection(projectId, id)

Delete a tag

Deletes a tag/collection. The prompts inside it are NOT deleted; only the grouping disappears. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CollectionsApi,
} from '@llmpulse/sdk';
import type { DeleteCollectionRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CollectionsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies DeleteCollectionRequest;

  try {
    const data = await api.deleteCollection(body);
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


## updateCollection

> updateCollection(id, updateCollectionRequest)

Update a tag

Renames a tag/collection or changes its description. Prompt membership is managed via POST /prompts/assign_tags, not here. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CollectionsApi,
} from '@llmpulse/sdk';
import type { UpdateCollectionOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CollectionsApi(config);

  const body = {
    // number
    id: 56,
    // UpdateCollectionRequest
    updateCollectionRequest: ...,
  } satisfies UpdateCollectionOperationRequest;

  try {
    const data = await api.updateCollection(body);
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
| **updateCollectionRequest** | [UpdateCollectionRequest](UpdateCollectionRequest.md) |  | |

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

