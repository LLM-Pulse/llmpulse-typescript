# HealthApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**ping**](HealthApi.md#ping) | **GET** /ping | Health check |



## ping

> Ping200Response ping(projectId)

Health check

Validates the API key and optionally pings a project. Returns the authenticated user_id, project (if project_id is supplied), and a request_id.

### Example

```ts
import {
  Configuration,
  HealthApi,
} from '@llmpulse/sdk';
import type { PingRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new HealthApi(config);

  const body = {
    // number | Optional project to verify access for (optional)
    projectId: 56,
  } satisfies PingRequest;

  try {
    const data = await api.ping(body);
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
| **projectId** | `number` | Optional project to verify access for | [Optional] [Defaults to `undefined`] |

### Return type

[**Ping200Response**](Ping200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | API is healthy |  -  |
| **401** | Authentication failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

