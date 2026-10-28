# APIKeysApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createApiKey**](APIKeysApi.md#createapikeyoperation) | **POST** /api_keys | Create an API key limited to projects |
| [**listApiKeys**](APIKeysApi.md#listapikeys) | **GET** /api_keys | List API keys |
| [**revokeApiKey**](APIKeysApi.md#revokeapikey) | **DELETE** /api_keys/{id} | Revoke an API key |



## createApiKey

> CreateApiKey201Response createApiKey(createApiKeyRequest)

Create an API key limited to projects

Creates an API key limited to the projects in project_ids, owned by the same user as the calling key, and returns its secret token once: store it, since it cannot be read again. The key sees only those projects (any other project answers ERR_PROJECT_NOT_FOUND) and cannot act on the whole account, and the set of projects never changes. This endpoint never creates an account-wide key; create one in the app under API Keys. scope is read (default) or read_write. Every project must be one the caller can access: a project of another account, a deleted one or an unknown id answers ERR_PROJECT_NOT_FOUND and nothing is created. A user can hold up to 500 active keys; past that the request answers ERR_LIMIT_REACHED until a key is revoked. Requires an account-wide &#x60;read_write&#x60; scope API key on the Scale plan or above: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. A team member needs permission to create API keys and can only choose projects they can access.

### Example

```ts
import {
  Configuration,
  APIKeysApi,
} from '@llmpulse/sdk';
import type { CreateApiKeyOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new APIKeysApi(config);

  const body = {
    // CreateApiKeyRequest
    createApiKeyRequest: ...,
  } satisfies CreateApiKeyOperationRequest;

  try {
    const data = await api.createApiKey(body);
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
| **createApiKeyRequest** | [CreateApiKeyRequest](CreateApiKeyRequest.md) |  | |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. The key as GET /api_keys lists it, plus its secret token, returned only this once. |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listApiKeys

> ListApiKeys200Response listApiKeys(page, perPage)

List API keys

Lists the API keys of the user the calling key belongs to, newest first, revoked ones included: name, the visible prefix of the token, scope (read or read_write), the projects a key is limited to (project_scoped, project_ids; an empty list on an account-wide key), when it was created and last used, and when it was revoked. The secret token is only ever returned once, by POST /api_keys. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan, so old keys can be found and revoked. A team member needs the API Keys permission and sees only their own keys.

### Example

```ts
import {
  Configuration,
  APIKeysApi,
} from '@llmpulse/sdk';
import type { ListApiKeysRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new APIKeysApi(config);

  const body = {
    // number (optional)
    page: 56,
    // number | Default 20, max 100 (optional)
    perPage: 56,
  } satisfies ListApiKeysRequest;

  try {
    const data = await api.listApiKeys(body);
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
| **page** | `number` |  | [Optional] [Defaults to `undefined`] |
| **perPage** | `number` | Default 20, max 100 | [Optional] [Defaults to `undefined`] |

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeApiKey

> RevokeApiKey200Response revokeApiKey(id)

Revoke an API key

Revokes an API key of the user the calling key belongs to: it stops working immediately and cannot be restored. Revoking a key that is already revoked answers the same way and keeps its original revocation time. A key of another user answers ERR_NOT_FOUND. The calling key can revoke itself. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan. A team member needs permission to delete API keys.

### Example

```ts
import {
  Configuration,
  APIKeysApi,
} from '@llmpulse/sdk';
import type { RevokeApiKeyRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new APIKeysApi(config);

  const body = {
    // number | The key id from GET /api_keys
    id: 56,
  } satisfies RevokeApiKeyRequest;

  try {
    const data = await api.revokeApiKey(body);
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
| **id** | `number` | The key id from GET /api_keys | [Defaults to `undefined`] |

### Return type

[**RevokeApiKey200Response**](RevokeApiKey200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

