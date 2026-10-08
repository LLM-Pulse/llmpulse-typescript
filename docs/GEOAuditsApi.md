# GEOAuditsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**compareGeoAuditRuns**](GEOAuditsApi.md#comparegeoauditruns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**createGeoAudits**](GEOAuditsApi.md#creategeoaudits) | **POST** /geo_audits | Create GEO audits |
| [**deleteGeoAudit**](GEOAuditsApi.md#deletegeoaudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**getGeoAudit**](GEOAuditsApi.md#getgeoaudit) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**getGeoAuditRun**](GEOAuditsApi.md#getgeoauditrun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**listGeoAlerts**](GEOAuditsApi.md#listgeoalerts) | **GET** /geo_alerts | List GEO audit alerts |
| [**listGeoAuditFindings**](GEOAuditsApi.md#listgeoauditfindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**listGeoAuditIssues**](GEOAuditsApi.md#listgeoauditissues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**listGeoAuditRuns**](GEOAuditsApi.md#listgeoauditruns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**listGeoAudits**](GEOAuditsApi.md#listgeoaudits) | **GET** /geo_audits | List GEO audits |
| [**runGeoAudit**](GEOAuditsApi.md#rungeoaudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**updateGeoAudit**](GEOAuditsApi.md#updategeoaudit) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**updateGeoAuditIssue**](GEOAuditsApi.md#updategeoauditissue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |



## compareGeoAuditRuns

> GeoAuditComparison compareGeoAuditRuns(projectId, id, fromRun, toRun)

Compare two GEO audit runs

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { CompareGeoAuditRunsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    id: id_example,
    // number | Run number to compare from (default the run before to_run) (optional)
    fromRun: 56,
    // number | Run number to compare to (default the latest completed run) (optional)
    toRun: 56,
  } satisfies CompareGeoAuditRunsRequest;

  try {
    const data = await api.compareGeoAuditRuns(body);
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
| **id** | `string` | Audit id | [Defaults to `undefined`] |
| **fromRun** | `number` | Run number to compare from (default the run before to_run) | [Optional] [Defaults to `undefined`] |
| **toRun** | `number` | Run number to compare to (default the latest completed run) | [Optional] [Defaults to `undefined`] |

### Return type

[**GeoAuditComparison**](GeoAuditComparison.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The comparison |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createGeoAudits

> GeoAuditCreateResponse createGeoAudits(geoAuditCreateRequest)

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { CreateGeoAuditsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // GeoAuditCreateRequest
    geoAuditCreateRequest: ...,
  } satisfies CreateGeoAuditsRequest;

  try {
    const data = await api.createGeoAudits(body);
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
| **geoAuditCreateRequest** | [GeoAuditCreateRequest](GeoAuditCreateRequest.md) |  | |

### Return type

[**GeoAuditCreateResponse**](GeoAuditCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created audits |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteGeoAudit

> GeoAuditArchived deleteGeoAudit(projectId, id)

Delete (archive) a GEO audit

Archives the audit. Requires a &#x60;read_write&#x60; scope API key and, for team members, delete permission on GEO Optimization.

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { DeleteGeoAuditRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    id: id_example,
  } satisfies DeleteGeoAuditRequest;

  try {
    const data = await api.deleteGeoAudit(body);
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
| **id** | `string` | Audit id | [Defaults to `undefined`] |

### Return type

[**GeoAuditArchived**](GeoAuditArchived.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Archived |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getGeoAudit

> GeoAuditResponse getGeoAudit(projectId, id)

Get a GEO audit

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { GetGeoAuditRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    id: id_example,
  } satisfies GetGeoAuditRequest;

  try {
    const data = await api.getGeoAudit(body);
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
| **id** | `string` | Audit id | [Defaults to `undefined`] |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The audit |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getGeoAuditRun

> GeoAuditRunDetail getGeoAuditRun(projectId, geoAuditId, sequence)

Get a GEO audit run

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { GetGeoAuditRunRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    geoAuditId: geoAuditId_example,
    // number | Run number within the audit
    sequence: 56,
  } satisfies GetGeoAuditRunRequest;

  try {
    const data = await api.getGeoAuditRun(body);
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
| **geoAuditId** | `string` | Audit id | [Defaults to `undefined`] |
| **sequence** | `number` | Run number within the audit | [Defaults to `undefined`] |

### Return type

[**GeoAuditRunDetail**](GeoAuditRunDetail.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The run with its result |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listGeoAlerts

> GeoAlertList listGeoAlerts(projectId, auditId, page, perPage)

List GEO audit alerts

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { ListGeoAlertsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Only alerts of this audit (optional)
    auditId: auditId_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListGeoAlertsRequest;

  try {
    const data = await api.listGeoAlerts(body);
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
| **auditId** | `string` | Only alerts of this audit | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

[**GeoAlertList**](GeoAlertList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated alerts |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listGeoAuditFindings

> GeoAuditFindingList listGeoAuditFindings(projectId, geoAuditId, sequence, page, perPage, output)

List the findings of a GEO audit run

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { ListGeoAuditFindingsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    geoAuditId: geoAuditId_example,
    // number | Run number within the audit
    sequence: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListGeoAuditFindingsRequest;

  try {
    const data = await api.listGeoAuditFindings(body);
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
| **geoAuditId** | `string` | Audit id | [Defaults to `undefined`] |
| **sequence** | `number` | Run number within the audit | [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**GeoAuditFindingList**](GeoAuditFindingList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated findings |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listGeoAuditIssues

> GeoAuditIssueList listGeoAuditIssues(projectId, geoAuditId, state, page, perPage)

List the issues of a GEO audit

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { ListGeoAuditIssuesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    geoAuditId: geoAuditId_example,
    // 'open' | 'accepted' | 'fixed' | 'gone' | open means open and not accepted; default all (optional)
    state: state_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListGeoAuditIssuesRequest;

  try {
    const data = await api.listGeoAuditIssues(body);
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
| **geoAuditId** | `string` | Audit id | [Defaults to `undefined`] |
| **state** | `open`, `accepted`, `fixed`, `gone` | open means open and not accepted; default all | [Optional] [Defaults to `undefined`] [Enum: open, accepted, fixed, gone] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

[**GeoAuditIssueList**](GeoAuditIssueList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated issues |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listGeoAuditRuns

> GeoAuditRunList listGeoAuditRuns(projectId, geoAuditId, page, perPage, output)

List the runs of a GEO audit

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { ListGeoAuditRunsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    geoAuditId: geoAuditId_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListGeoAuditRunsRequest;

  try {
    const data = await api.listGeoAuditRuns(body);
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
| **geoAuditId** | `string` | Audit id | [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**GeoAuditRunList**](GeoAuditRunList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated runs |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listGeoAudits

> GeoAuditList listGeoAudits(projectId, auditType, status, cadence, page, perPage)

List GEO audits

Lists the project\&#39;s audits, most recently updated first. Archived audits are left out unless status&#x3D;archived.

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { ListGeoAuditsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // 'agent_readiness' | 'robots_txt' | 'crawlability' | 'schema' | 'content_readiness' | 'discoverability' | 'site_structure' (optional)
    auditType: auditType_example,
    // 'active' | 'paused' | 'archived' (optional)
    status: status_example,
    // 'once' | 'weekly' | 'monthly' (optional)
    cadence: cadence_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListGeoAuditsRequest;

  try {
    const data = await api.listGeoAudits(body);
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
| **auditType** | `agent_readiness`, `robots_txt`, `crawlability`, `schema`, `content_readiness`, `discoverability`, `site_structure` |  | [Optional] [Defaults to `undefined`] [Enum: agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure] |
| **status** | `active`, `paused`, `archived` |  | [Optional] [Defaults to `undefined`] [Enum: active, paused, archived] |
| **cadence** | `once`, `weekly`, `monthly` |  | [Optional] [Defaults to `undefined`] [Enum: once, weekly, monthly] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |

### Return type

[**GeoAuditList**](GeoAuditList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated audits |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## runGeoAudit

> GeoAuditRunResponse runGeoAudit(projectId, geoAuditId)

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { RunGeoAuditRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // string | Audit id
    geoAuditId: geoAuditId_example,
  } satisfies RunGeoAuditRequest;

  try {
    const data = await api.runGeoAudit(body);
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
| **geoAuditId** | `string` | Audit id | [Defaults to `undefined`] |

### Return type

[**GeoAuditRunResponse**](GeoAuditRunResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The new run |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateGeoAudit

> GeoAuditResponse updateGeoAudit(id, geoAuditUpdateRequest)

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { UpdateGeoAuditRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // string | Audit id
    id: id_example,
    // GeoAuditUpdateRequest
    geoAuditUpdateRequest: ...,
  } satisfies UpdateGeoAuditRequest;

  try {
    const data = await api.updateGeoAudit(body);
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
| **id** | `string` | Audit id | [Defaults to `undefined`] |
| **geoAuditUpdateRequest** | [GeoAuditUpdateRequest](GeoAuditUpdateRequest.md) |  | |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated audit |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateGeoAuditIssue

> GeoAuditIssueResponse updateGeoAuditIssue(geoAuditId, id, geoAuditIssueUpdateRequest)

Accept or reopen a GEO audit issue

Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example

```ts
import {
  Configuration,
  GEOAuditsApi,
} from '@llmpulse/sdk';
import type { UpdateGeoAuditIssueRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new GEOAuditsApi(config);

  const body = {
    // string | Audit id
    geoAuditId: geoAuditId_example,
    // number | Issue id
    id: 56,
    // GeoAuditIssueUpdateRequest
    geoAuditIssueUpdateRequest: ...,
  } satisfies UpdateGeoAuditIssueRequest;

  try {
    const data = await api.updateGeoAuditIssue(body);
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
| **geoAuditId** | `string` | Audit id | [Defaults to `undefined`] |
| **id** | `number` | Issue id | [Defaults to `undefined`] |
| **geoAuditIssueUpdateRequest** | [GeoAuditIssueUpdateRequest](GeoAuditIssueUpdateRequest.md) |  | |

### Return type

[**GeoAuditIssueResponse**](GeoAuditIssueResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated issue |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

