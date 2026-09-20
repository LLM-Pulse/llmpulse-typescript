# GEOWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createIntelligenceTask**](GEOWriterApi.md#createintelligencetask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**getIntelligenceTask**](GEOWriterApi.md#getintelligencetask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**listIntelligenceTasks**](GEOWriterApi.md#listintelligencetasks) | **GET** /intelligence_tasks | List GEO Writer tasks |
| [**revertIntelligenceTaskContent**](GEOWriterApi.md#revertintelligencetaskcontent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**updateIntelligenceTaskContent**](GEOWriterApi.md#updateintelligencetaskcontent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |



## createIntelligenceTask

> IntelligenceTask createIntelligenceTask(intelligenceTaskCreateRequest)

Create a GEO Writer task

### Example

```ts
import {
  Configuration,
  GEOWriterApi,
} from '@llmpulse/sdk';
import type { CreateIntelligenceTaskRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOWriterApi(config);

  const body = {
    // IntelligenceTaskCreateRequest
    intelligenceTaskCreateRequest: ...,
  } satisfies CreateIntelligenceTaskRequest;

  try {
    const data = await api.createIntelligenceTask(body);
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
| **intelligenceTaskCreateRequest** | [IntelligenceTaskCreateRequest](IntelligenceTaskCreateRequest.md) |  | |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

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


## getIntelligenceTask

> IntelligenceTask getIntelligenceTask(projectId, id)

Get a GEO Writer task

### Example

```ts
import {
  Configuration,
  GEOWriterApi,
} from '@llmpulse/sdk';
import type { GetIntelligenceTaskRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOWriterApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Numeric task ID or public_id string token
    id: id_example,
  } satisfies GetIntelligenceTaskRequest;

  try {
    const data = await api.getIntelligenceTask(body);
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
| **id** | `string` | Numeric task ID or public_id string token | [Defaults to `undefined`] |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Task with result_data when completed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listIntelligenceTasks

> listIntelligenceTasks(projectId, taskType, status, page, perPage)

List GEO Writer tasks

### Example

```ts
import {
  Configuration,
  GEOWriterApi,
} from '@llmpulse/sdk';
import type { ListIntelligenceTasksRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOWriterApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'brief' | 'create' | 'update' | 'pr_insights' | 'custom' (optional)
    taskType: taskType_example,
    // string (optional)
    status: status_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListIntelligenceTasksRequest;

  try {
    const data = await api.listIntelligenceTasks(body);
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
| **taskType** | `brief`, `create`, `update`, `pr_insights`, `custom` |  | [Optional] [Defaults to `undefined`] [Enum: brief, create, update, pr_insights, custom] |
| **status** | `string` |  | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

`void` (Empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tasks |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revertIntelligenceTaskContent

> IntelligenceTask revertIntelligenceTaskContent(projectId, id)

Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

### Example

```ts
import {
  Configuration,
  GEOWriterApi,
} from '@llmpulse/sdk';
import type { RevertIntelligenceTaskContentRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOWriterApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Numeric task ID or public_id string token
    id: id_example,
  } satisfies RevertIntelligenceTaskContentRequest;

  try {
    const data = await api.revertIntelligenceTaskContent(body);
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
| **id** | `string` | Numeric task ID or public_id string token | [Defaults to `undefined`] |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Task restored to its generated output |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateIntelligenceTaskContent

> IntelligenceTaskUpdateResponse updateIntelligenceTaskContent(id, intelligenceTaskUpdateRequest)

Edit GEO Writer task content

Edits the text of a completed task in place. &#x60;edits&#x60; maps dotted paths into result_data (for example &#x60;title&#x60; or &#x60;sections.0.content&#x60;) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank &#x60;title&#x60;, a value over 20,000 characters or an empty &#x60;edits&#x60; object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

### Example

```ts
import {
  Configuration,
  GEOWriterApi,
} from '@llmpulse/sdk';
import type { UpdateIntelligenceTaskContentRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOWriterApi(config);

  const body = {
    // string | Numeric task ID or public_id string token
    id: id_example,
    // IntelligenceTaskUpdateRequest
    intelligenceTaskUpdateRequest: ...,
  } satisfies UpdateIntelligenceTaskContentRequest;

  try {
    const data = await api.updateIntelligenceTaskContent(body);
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
| **id** | `string` | Numeric task ID or public_id string token | [Defaults to `undefined`] |
| **intelligenceTaskUpdateRequest** | [IntelligenceTaskUpdateRequest](IntelligenceTaskUpdateRequest.md) |  | |

### Return type

[**IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated task with the paths that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

