# CustomReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getCustomReport**](CustomReportsApi.md#getcustomreport) | **GET** /custom_reports/{id} | Get a custom report with its widget data |
| [**listCustomReports**](CustomReportsApi.md#listcustomreports) | **GET** /custom_reports | List custom reports |
| [**sendCustomReport**](CustomReportsApi.md#sendcustomreportoperation) | **POST** /custom_reports/{id}/send | Send a custom report now |



## getCustomReport

> CustomReportDetailResponse getCustomReport(projectId, id)

Get a custom report with its widget data

The configuration of one custom report (date range, filters, schedule, layout) and the data of every widget computed for today, the same numbers the report page, its shared link and its PDF show. Each widget carries its &#x60;kind&#x60; and a &#x60;data&#x60; object shaped by it: &#x60;series&#x60; for &#x60;timeseries&#x60;, &#x60;slices&#x60; for &#x60;donut&#x60;, &#x60;bars&#x60; for &#x60;bar&#x60;, &#x60;values&#x60; and &#x60;changes&#x60; for &#x60;kpi_grid&#x60;, &#x60;rows&#x60; for &#x60;table&#x60;. A widget whose data source is not connected has &#x60;available: false&#x60; and &#x60;data: null&#x60;. Nothing is saved or sent. Requires the Scale plan or above.

### Example

```ts
import {
  Configuration,
  CustomReportsApi,
} from '@llmpulse/sdk';
import type { GetCustomReportRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CustomReportsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number | Custom report id, from GET /custom_reports
    id: 56,
  } satisfies GetCustomReportRequest;

  try {
    const data = await api.getCustomReport(body);
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
| **id** | `number` | Custom report id, from GET /custom_reports | [Defaults to `undefined`] |

### Return type

[**CustomReportDetailResponse**](CustomReportDetailResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Report configuration and widget data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCustomReports

> CustomReportsResponse listCustomReports(projectId, page, perPage, output)

List custom reports

The custom reports of the project, newest first, as the Reports &gt; Custom Reports list shows them. Recipient addresses, the shared-link token and the password are never returned. Requires the Scale plan or above.

### Example

```ts
import {
  Configuration,
  CustomReportsApi,
} from '@llmpulse/sdk';
import type { ListCustomReportsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CustomReportsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListCustomReportsRequest;

  try {
    const data = await api.listCustomReports(body);
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
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**CustomReportsResponse**](CustomReportsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated custom reports |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## sendCustomReport

> CustomReportSendResponse sendCustomReport(id, sendCustomReportRequest)

Send a custom report now

Queues the report\&#39;s PDF for its recipients, like the Send now button on the report page: the report must be published and have at least one recipient (ERR_INVALID_PARAM otherwise), and each report can be sent once every 10 minutes (429 ERR_RATE_LIMITED with Retry-After). Not available from a white-label portal or for a report made inside one (ERR_INTEGRATION_UNAVAILABLE). Requires the Scale plan or above, a &#x60;read_write&#x60; scope API key and, for team members, update permission on Custom Reports.

### Example

```ts
import {
  Configuration,
  CustomReportsApi,
} from '@llmpulse/sdk';
import type { SendCustomReportOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CustomReportsApi(config);

  const body = {
    // number | Custom report id, from GET /custom_reports
    id: 56,
    // SendCustomReportRequest
    sendCustomReportRequest: ...,
  } satisfies SendCustomReportOperationRequest;

  try {
    const data = await api.sendCustomReport(body);
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
| **id** | `number` | Custom report id, from GET /custom_reports | [Defaults to `undefined`] |
| **sendCustomReportRequest** | [SendCustomReportRequest](SendCustomReportRequest.md) |  | |

### Return type

[**CustomReportSendResponse**](CustomReportSendResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The report is queued for its recipients |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, a team member without the permission ERR_INSUFFICIENT_PERMISSION, and a request made on a white-label portal host, where the app does not offer this action, ERR_INTEGRATION_UNAVAILABLE, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **429** | The report was sent less than 10 minutes ago; retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

