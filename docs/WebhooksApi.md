# WebhooksApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createWebhook**](WebhooksApi.md#createwebhookoperation) | **POST** /webhooks | Create a webhook subscription |
| [**deleteWebhook**](WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription |
| [**listWebhooks**](WebhooksApi.md#listwebhooks) | **GET** /webhooks | List webhook subscriptions |
| [**sampleWebhookPayloads**](WebhooksApi.md#samplewebhookpayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads |



## createWebhook

> CreateWebhook201Response createWebhook(createWebhookRequest)

Create a webhook subscription

Subscribes a public HTTPS URL to a project event. LLM Pulse POSTs a JSON envelope (&#x60;event&#x60;, &#x60;occurred_at&#x60;, &#x60;project_id&#x60;, &#x60;subscription_id&#x60;, &#x60;data&#x60;) to the URL every time the event occurs, signed via the &#x60;X-LLMPulse-Signature&#x60; header (HMAC-SHA256 of the raw body computed with the subscription secret). Failed deliveries receive up to 5 attempts in total, including the first, with backoff; subscriptions auto-disable after 20 consecutive failed deliveries. Idempotent for the same project + event + URL. Requires a &#x60;read_write&#x60; scope API key and the Scale plan or above.

### Example

```ts
import {
  Configuration,
  WebhooksApi,
} from '@llmpulse/sdk';
import type { CreateWebhookOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WebhooksApi(config);

  const body = {
    // CreateWebhookRequest
    createWebhookRequest: ...,
  } satisfies CreateWebhookOperationRequest;

  try {
    const data = await api.createWebhook(body);
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
| **createWebhookRequest** | [CreateWebhookRequest](CreateWebhookRequest.md) |  | |

### Return type

[**CreateWebhook201Response**](CreateWebhook201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. The signing secret is only returned by this endpoint. |  -  |
| **401** | Authentication failed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteWebhook

> DeleteWebhook200Response deleteWebhook(id)

Delete a webhook subscription

Deletes a webhook subscription; the target URL stops receiving events immediately. Requires a &#x60;read_write&#x60; scope API key and the Scale plan or above.

### Example

```ts
import {
  Configuration,
  WebhooksApi,
} from '@llmpulse/sdk';
import type { DeleteWebhookRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WebhooksApi(config);

  const body = {
    // number
    id: 56,
  } satisfies DeleteWebhookRequest;

  try {
    const data = await api.deleteWebhook(body);
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

### Return type

[**DeleteWebhook200Response**](DeleteWebhook200Response.md)

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
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listWebhooks

> ListWebhooks200Response listWebhooks(projectId, page, perPage)

List webhook subscriptions

Lists active webhook subscriptions for the account, optionally filtered by project. Requires the Scale plan or above.

### Example

```ts
import {
  Configuration,
  WebhooksApi,
} from '@llmpulse/sdk';
import type { ListWebhooksRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WebhooksApi(config);

  const body = {
    // number | Optional project filter (optional)
    projectId: 56,
    // number (optional)
    page: 56,
    // number | Max 100 (optional)
    perPage: 56,
  } satisfies ListWebhooksRequest;

  try {
    const data = await api.listWebhooks(body);
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
| **projectId** | `number` | Optional project filter | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `undefined`] |
| **perPage** | `number` | Max 100 | [Optional] [Defaults to `undefined`] |

### Return type

[**ListWebhooks200Response**](ListWebhooks200Response.md)

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
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## sampleWebhookPayloads

> SampleWebhookPayloads200Response sampleWebhookPayloads(eventType, projectId)

Sample event payloads

Returns up to 3 example event payloads for the event type, built from the project\&#39;s most recent real data (or a static sample when the project has no data). Used by integration editors such as the Zapier sample loader. Requires the Scale plan or above.

### Example

```ts
import {
  Configuration,
  WebhooksApi,
} from '@llmpulse/sdk';
import type { SampleWebhookPayloadsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WebhooksApi(config);

  const body = {
    // 'mention.created' | 'competitor_mention.created' | 'citation.created' | 'prompt_execution.completed' | 'sentiment.negative_detected' | 'recommendation.completed' | 'intelligence_task.completed' | 'intelligence_task.updated'
    eventType: eventType_example,
    // number
    projectId: 56,
  } satisfies SampleWebhookPayloadsRequest;

  try {
    const data = await api.sampleWebhookPayloads(body);
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
| **eventType** | `mention.created`, `competitor_mention.created`, `citation.created`, `prompt_execution.completed`, `sentiment.negative_detected`, `recommendation.completed`, `intelligence_task.completed`, `intelligence_task.updated` |  | [Defaults to `undefined`] [Enum: mention.created, competitor_mention.created, citation.created, prompt_execution.completed, sentiment.negative_detected, recommendation.completed, intelligence_task.completed, intelligence_task.updated] |
| **projectId** | `number` |  | [Defaults to `undefined`] |

### Return type

[**SampleWebhookPayloads200Response**](SampleWebhookPayloads200Response.md)

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
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

