# CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCompetitor**](CompetitorsApi.md#createcompetitoroperation) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor**](CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**getCompetitorDetails**](CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**listCompetitors**](CompetitorsApi.md#listcompetitors) | **GET** /dimensions/competitors | List competitors |
| [**updateCompetitor**](CompetitorsApi.md#updatecompetitoroperation) | **PATCH** /competitors/{id} | Update a competitor |



## createCompetitor

> CompetitorCreateResponse createCompetitor(createCompetitorRequest)

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { CreateCompetitorOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // CreateCompetitorRequest
    createCompetitorRequest: ...,
  } satisfies CreateCompetitorOperationRequest;

  try {
    const data = await api.createCompetitor(body);
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
| **createCompetitorRequest** | [CreateCompetitorRequest](CreateCompetitorRequest.md) |  | |

### Return type

[**CompetitorCreateResponse**](CompetitorCreateResponse.md)

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


## deleteCompetitor

> deleteCompetitor(projectId, id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; its tracked data is purged by a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { DeleteCompetitorRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies DeleteCompetitorRequest;

  try {
    const data = await api.deleteCompetitor(body);
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


## getCompetitorDetails

> CompetitorDetails getCompetitorDetails(projectId, id)

Competitor details

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { GetCompetitorDetailsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies GetCompetitorDetailsRequest;

  try {
    const data = await api.getCompetitorDetails(body);
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

[**CompetitorDetails**](CompetitorDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitor details |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listCompetitors

> ListCompetitors200Response listCompetitors(projectId, includeProjectBrand, output)

List competitors

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { ListCompetitorsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // boolean | When true, prepends the project brand with actor_type=project and is_own=true (optional)
    includeProjectBrand: true,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListCompetitorsRequest;

  try {
    const data = await api.listCompetitors(body);
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
| **includeProjectBrand** | `boolean` | When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [Optional] [Defaults to `false`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**ListCompetitors200Response**](ListCompetitors200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitors |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateCompetitor

> updateCompetitor(id, updateCompetitorRequest)

Update a competitor

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing&#x3D;true for a few minutes and further edits are rejected meanwhile. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { UpdateCompetitorOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new CompetitorsApi(config);

  const body = {
    // number
    id: 56,
    // UpdateCompetitorRequest
    updateCompetitorRequest: ...,
  } satisfies UpdateCompetitorOperationRequest;

  try {
    const data = await api.updateCompetitor(body);
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
| **updateCompetitorRequest** | [UpdateCompetitorRequest](UpdateCompetitorRequest.md) |  | |

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
| **200** | Updated |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

