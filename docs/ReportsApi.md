# ReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTechnicalGeoReports**](ReportsApi.md#createtechnicalgeoreportsoperation) | **POST** /technical_geo_reports | Run technical GEO analysis |



## createTechnicalGeoReports

> createTechnicalGeoReports(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  ReportsApi,
} from '@llmpulse/sdk';
import type { CreateTechnicalGeoReportsOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ReportsApi(config);

  const body = {
    // CreateTechnicalGeoReportsRequest
    createTechnicalGeoReportsRequest: ...,
  } satisfies CreateTechnicalGeoReportsOperationRequest;

  try {
    const data = await api.createTechnicalGeoReports(body);
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
| **createTechnicalGeoReportsRequest** | [CreateTechnicalGeoReportsRequest](CreateTechnicalGeoReportsRequest.md) |  | |

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

