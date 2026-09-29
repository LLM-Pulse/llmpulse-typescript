# TechnicalGEOReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTechnicalGeoReports**](TechnicalGEOReportsApi.md#createtechnicalgeoreportsoperation) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport**](TechnicalGEOReportsApi.md#gettechnicalgeoreport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports**](TechnicalGEOReportsApi.md#listtechnicalgeoreports) | **GET** /technical_geo_reports | List technical GEO reports |
| [**revertTechnicalGeoReportContent**](TechnicalGEOReportsApi.md#reverttechnicalgeoreportcontent) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content |
| [**updateTechnicalGeoReportContent**](TechnicalGEOReportsApi.md#updatetechnicalgeoreportcontent) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content |



## createTechnicalGeoReports

> createTechnicalGeoReports(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

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

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website\&#39;s own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

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


## revertTechnicalGeoReportContent

> LlmsTxtTechnicalGeoReport revertTechnicalGeoReportContent(id, technicalGeoReportContentRevertRequest)

Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example

```ts
import {
  Configuration,
  TechnicalGEOReportsApi,
} from '@llmpulse/sdk';
import type { RevertTechnicalGeoReportContentRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TechnicalGEOReportsApi(config);

  const body = {
    // number | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
    id: 56,
    // TechnicalGeoReportContentRevertRequest
    technicalGeoReportContentRevertRequest: ...,
  } satisfies RevertTechnicalGeoReportContentRequest;

  try {
    const data = await api.revertTechnicalGeoReportContent(body);
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
| **id** | `number` | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | [Defaults to `undefined`] |
| **technicalGeoReportContentRevertRequest** | [TechnicalGeoReportContentRevertRequest](TechnicalGeoReportContentRevertRequest.md) |  | |

### Return type

[**LlmsTxtTechnicalGeoReport**](LlmsTxtTechnicalGeoReport.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report with its generated files restored |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTechnicalGeoReportContent

> TechnicalGeoReportContentUpdateResponse updateTechnicalGeoReportContent(id, technicalGeoReportContentUpdateRequest)

Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. &#x60;edits&#x60; maps llms_txt and/or llms_full_txt to the full replacement text. &#x60;content_version&#x60; must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty &#x60;edits&#x60; object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example

```ts
import {
  Configuration,
  TechnicalGEOReportsApi,
} from '@llmpulse/sdk';
import type { UpdateTechnicalGeoReportContentRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TechnicalGEOReportsApi(config);

  const body = {
    // number | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
    id: 56,
    // TechnicalGeoReportContentUpdateRequest
    technicalGeoReportContentUpdateRequest: ...,
  } satisfies UpdateTechnicalGeoReportContentRequest;

  try {
    const data = await api.updateTechnicalGeoReportContent(body);
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
| **id** | `number` | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | [Defaults to `undefined`] |
| **technicalGeoReportContentUpdateRequest** | [TechnicalGeoReportContentUpdateRequest](TechnicalGeoReportContentUpdateRequest.md) |  | |

### Return type

[**TechnicalGeoReportContentUpdateResponse**](TechnicalGeoReportContentUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report with its current files, plus the files that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

