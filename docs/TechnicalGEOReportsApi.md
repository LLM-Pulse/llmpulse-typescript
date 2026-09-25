# TechnicalGEOReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTechnicalGeoReports**](TechnicalGEOReportsApi.md#createtechnicalgeoreportsoperation) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport**](TechnicalGEOReportsApi.md#gettechnicalgeoreport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports**](TechnicalGEOReportsApi.md#listtechnicalgeoreports) | **GET** /technical_geo_reports | List technical GEO reports |



## createTechnicalGeoReports

> createTechnicalGeoReports(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full technical GEO analysis bundle (crawlability, schema, content readiness, discoverability, site structure, robots.txt, agent readiness, llms.txt, AI visibility) for a URL + country. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  TechnicalGEOReportsApi,
} from '@llmpulse/sdk';
import type { CreateTechnicalGeoReportsOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TechnicalGEOReportsApi(config);

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
| **201** | Created. app_urls maps each created report type to the link that opens that report in the app |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTechnicalGeoReport

> getTechnicalGeoReport(projectId, reportType, id)

Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report left on the website\&#39;s own language in the app, and for every other report type); a completed llms_txt result_data also returns manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, set once the customer edited the files in the app) and metadata.output_language_code.

### Example

```ts
import {
  Configuration,
  TechnicalGEOReportsApi,
} from '@llmpulse/sdk';
import type { GetTechnicalGeoReportRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TechnicalGEOReportsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'crawlability' | 'schema' | 'content_readiness' | 'discoverability' | 'site_structure' | 'robots_txt' | 'agent_readiness' | 'llms_txt' | 'ai_visibility'
    reportType: reportType_example,
    // number | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
    id: 56,
  } satisfies GetTechnicalGeoReportRequest;

  try {
    const data = await api.getTechnicalGeoReport(body);
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
| **reportType** | `crawlability`, `schema`, `content_readiness`, `discoverability`, `site_structure`, `robots_txt`, `agent_readiness`, `llms_txt`, `ai_visibility` |  | [Defaults to `undefined`] [Enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **id** | `number` | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | [Defaults to `undefined`] |

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
| **200** | Report status and completed result data, plus app_url, the link that opens the report in the app |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTechnicalGeoReports

> listTechnicalGeoReports(projectId, reportType, status, batchId, page, perPage)

List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Example

```ts
import {
  Configuration,
  TechnicalGEOReportsApi,
} from '@llmpulse/sdk';
import type { ListTechnicalGeoReportsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TechnicalGEOReportsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'crawlability' | 'schema' | 'content_readiness' | 'discoverability' | 'site_structure' | 'robots_txt' | 'agent_readiness' | 'llms_txt' | 'ai_visibility'
    reportType: reportType_example,
    // string | Optional status filter; valid values depend on report_type (optional)
    status: status_example,
    // number | Optional batch id returned when the report bundle was created (optional)
    batchId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListTechnicalGeoReportsRequest;

  try {
    const data = await api.listTechnicalGeoReports(body);
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
| **reportType** | `crawlability`, `schema`, `content_readiness`, `discoverability`, `site_structure`, `robots_txt`, `agent_readiness`, `llms_txt`, `ai_visibility` |  | [Defaults to `undefined`] [Enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **status** | `string` | Optional status filter; valid values depend on report_type | [Optional] [Defaults to `undefined`] |
| **batchId** | `number` | Optional batch id returned when the report bundle was created | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

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
| **200** | Paginated technical GEO report summaries. Every summary carries app_url, the link that opens the report in the app |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

