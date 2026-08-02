# PromptsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**assignPromptTags**](PromptsApi.md#assignprompttagsoperation) | **POST** /prompts/assign_tags | Bulk-attach tags to prompts |
| [**createPrompts**](PromptsApi.md#createprompts) | **POST** /prompts | Bulk-create prompts |
| [**deletePrompt**](PromptsApi.md#deleteprompt) | **DELETE** /prompts/{id} | Delete a prompt |



## assignPromptTags

> assignPromptTags(assignPromptTagsRequest)

Bulk-attach tags to prompts

Idempotent bulk assignment of tags (Collections) to existing prompts. Tags can be resolved by id or by name (case-insensitive). Use &#x60;create_missing: true&#x60; to auto-create unknown tag names. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { AssignPromptTagsOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // AssignPromptTagsRequest
    assignPromptTagsRequest: ...,
  } satisfies AssignPromptTagsOperationRequest;

  try {
    const data = await api.assignPromptTags(body);
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
| **assignPromptTagsRequest** | [AssignPromptTagsRequest](AssignPromptTagsRequest.md) |  | |

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
| **200** | Tags attached |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createPrompts

> PromptsCreateResponse createPrompts(promptsCreateRequest)

Bulk-create prompts

Add prompts to a project in bulk (up to 100 per request). Validates the account prompt quota and skips duplicates. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { CreatePromptsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // PromptsCreateRequest
    promptsCreateRequest: ...,
  } satisfies CreatePromptsRequest;

  try {
    const data = await api.createPrompts(body);
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
| **promptsCreateRequest** | [PromptsCreateRequest](PromptsCreateRequest.md) |  | |

### Return type

[**PromptsCreateResponse**](PromptsCreateResponse.md)

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


## deletePrompt

> deletePrompt(projectId, id)

Delete a prompt

Deletes a prompt (irreversible). The prompt disappears immediately and frees a prompt slot; its historical data (executions, mentions, citations, sentiment) is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  PromptsApi,
} from '@llmpulse/sdk';
import type { DeletePromptRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new PromptsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies DeletePromptRequest;

  try {
    const data = await api.deletePrompt(body);
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

