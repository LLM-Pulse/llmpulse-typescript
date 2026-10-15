# CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCompetitor**](CompetitorsApi.md#createcompetitoroperation) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor**](CompetitorsApi.md#deletecompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**getCompetitorDetails**](CompetitorsApi.md#getcompetitordetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**listCompetitorSuggestions**](CompetitorsApi.md#listcompetitorsuggestions) | **GET** /competitors/suggestions | List competitor suggestions |
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

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; a background job then deletes its mentions, citations, sentiment and share of voice history. Its ads, shopping products, local businesses and brand entities are kept and move to the project or another competitor they match, or stay unattributed. Requires a &#x60;read_write&#x60; scope API key.

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


## listCompetitorSuggestions

> CompetitorSuggestionsResponse listCompetitorSuggestions(projectId, basis, query, page, perPage, output)

List competitor suggestions

The two lists of the Suggested tab of the Competitors page. &#x60;basis&#x3D;brands&#x60; (default) returns the competing brands the AI discovery proposed that are not tracked or rejected yet, with the names it would match and, when counted, how many answers name it (&#x60;mentions&#x60;). &#x60;basis&#x3D;citations&#x60; returns the domains AI answers cite most that are not your own or tracked yet, with how many answers cite each (&#x60;citations&#x60;). &#x60;discovery&#x60; tells whether a discovery run is still loading. Read-only: it never starts a discovery run, which the page starts from its Discover button. Add a suggestion with POST /competitors.

### Example

```ts
import {
  Configuration,
  CompetitorsApi,
} from '@llmpulse/sdk';
import type { ListCompetitorSuggestionsRequest } from '@llmpulse/sdk';

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
    // 'brands' | 'citations' (optional)
    basis: basis_example,
    // string | Only suggestions whose brand name or domain contains this text (optional)
    query: query_example,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListCompetitorSuggestionsRequest;

  try {
    const data = await api.listCompetitorSuggestions(body);
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
| **basis** | `brands`, `citations` |  | [Optional] [Defaults to `&#39;brands&#39;`] [Enum: brands, citations] |
| **query** | `string` | Only suggestions whose brand name or domain contains this text | [Optional] [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **perPage** | `number` |  | [Optional] [Defaults to `20`] |
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**CompetitorSuggestionsResponse**](CompetitorSuggestionsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **422** | Invalid parameters |  -  |

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

