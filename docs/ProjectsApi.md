# ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createProject**](ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode) |
| [**createProjectDraft**](ProjectsApi.md#createprojectdraftoperation) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**deleteProject**](ProjectsApi.md#deleteproject) | **DELETE** /projects/{id} | Delete a project |
| [**finalizeProjectDraft**](ProjectsApi.md#finalizeprojectdraftoperation) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**getProjectDetails**](ProjectsApi.md#getprojectdetails) | **GET** /dimensions/projects/{id} | Project details |
| [**getProjectDraft**](ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**listLocales**](ProjectsApi.md#listlocales) | **GET** /dimensions/locales | List locales with data |
| [**listModels**](ProjectsApi.md#listmodels) | **GET** /dimensions/models | List models with data |
| [**listProjects**](ProjectsApi.md#listprojects) | **GET** /dimensions/projects | List projects |
| [**updateProject**](ProjectsApi.md#updateprojectoperation) | **PATCH** /projects/{id} | Update a project profile (Brand Book) |
| [**updateProjectDraft**](ProjectsApi.md#updateprojectdraftoperation) | **PATCH** /project_drafts/{id} | Submit a wizard step |



## createProject

> ProjectCreateResponse createProject(projectCreateRequest)

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), collections tagging those prompts, competitors, weekly email subscription. The response lists same_domain_projects so an accidental duplicate is visible; it never blocks the create. Idempotent via &#x60;external_identifier&#x60; (embed-enabled accounts only; replay returns 200 with the existing project). Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { CreateProjectRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // ProjectCreateRequest
    projectCreateRequest: ...,
  } satisfies CreateProjectRequest;

  try {
    const data = await api.createProject(body);
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
| **projectCreateRequest** | [ProjectCreateRequest](ProjectCreateRequest.md) |  | |

### Return type

[**ProjectCreateResponse**](ProjectCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **200** | Idempotent replay (existing external_identifier) |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createProjectDraft

> createProjectDraft(createProjectDraftRequest)

Start a project draft (wizard step 1)

Start the multi-step project-creation wizard. Returns a draft_id plus AI suggestions (name, description, industry, brand aliases) for the URL. Cold URLs can take up to ~2 minutes to analyze; pass suggest&#x3D;false to skip AI and respond instantly. Drafts expire after 24h. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { CreateProjectDraftOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // CreateProjectDraftRequest
    createProjectDraftRequest: ...,
  } satisfies CreateProjectDraftOperationRequest;

  try {
    const data = await api.createProjectDraft(body);
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
| **createProjectDraftRequest** | [CreateProjectDraftRequest](CreateProjectDraftRequest.md) |  | |

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
| **201** | Draft created; envelope with draft state, suggestions and limits |  -  |
| **422** | Invalid parameters |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteProject

> ProjectDeleteResponse deleteProject(id)

Delete a project

Deletes a project, like Delete Project in Project Settings, and cannot be undone. The project disappears at once from the app, GET /dimensions/projects and every other endpoint, and frees a project slot; a background job then deletes its prompts, answers, mentions, citations, sentiment, competitors and metrics history. API keys limited to it lose it, and a key left with no project is revoked. A project that is already being deleted, or that the key cannot see, answers ERR_PROJECT_NOT_FOUND. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. A team member needs permission to delete projects.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { DeleteProjectRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // number
    id: 56,
  } satisfies DeleteProjectRequest;

  try {
    const data = await api.deleteProject(body);
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

[**ProjectDeleteResponse**](ProjectDeleteResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Deleted |  -  |
| **403** | A read-only key answers ERR_INSUFFICIENT_SCOPE and a key limited to some projects ERR_KEY_PROJECT_SCOPED: deleting a project acts on the whole account. A team member whose permissions do not grant deleting projects answers ERR_INSUFFICIENT_PERMISSION. All with the same status, and nothing is deleted |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## finalizeProjectDraft

> finalizeProjectDraft(id, finalizeProjectDraftRequest)

Finalize a draft into a real project

Creates the project with all accumulated draft data (same effects as POST /projects). Idempotent: finalizing an already-finalized draft returns 200 with the existing project. Optional overrides: weekly_email_subscribed, execute_prompts_immediately.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { FinalizeProjectDraftOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: id_example,
    // FinalizeProjectDraftRequest (optional)
    finalizeProjectDraftRequest: ...,
  } satisfies FinalizeProjectDraftOperationRequest;

  try {
    const data = await api.finalizeProjectDraft(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |
| **finalizeProjectDraftRequest** | [FinalizeProjectDraftRequest](FinalizeProjectDraftRequest.md) |  | [Optional] |

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
| **201** | Project created |  -  |
| **200** | Idempotent replay |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getProjectDetails

> ProjectDetails getProjectDetails(id)

Project details

Detailed info for one project: matching_names, additional_owned_domains, industry, business model, primary products, target audience, brand voice, locale, app store IDs, prompt_limit (the project\&#39;s own prompt cap, null without one), stats (incl. prompts_by_brand_kind counts and prompts_available, how many prompts can still be added: the lower of the project\&#39;s free slots and the account\&#39;s remaining prompts, null when neither caps it), data_coverage (models, countries and languages with data) and the status of each data connection (search_console, ai_traffic, agent_traffic) with the connect_url where the user connects it.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { GetProjectDetailsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // number
    id: 56,
  } satisfies GetProjectDetailsRequest;

  try {
    const data = await api.getProjectDetails(body);
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

[**ProjectDetails**](ProjectDetails.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Project details |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getProjectDraft

> getProjectDraft(id, includeSuggestions)

Read a project draft

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { GetProjectDraftRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string | Draft id (draft_...)
    id: id_example,
    // boolean | Cache-only: returns suggestions for the current step if already generated, never triggers AI (optional)
    includeSuggestions: true,
  } satisfies GetProjectDraftRequest;

  try {
    const data = await api.getProjectDraft(body);
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
| **id** | `string` | Draft id (draft_...) | [Defaults to `undefined`] |
| **includeSuggestions** | `boolean` | Cache-only: returns suggestions for the current step if already generated, never triggers AI | [Optional] [Defaults to `false`] |

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
| **200** | Draft envelope |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listLocales

> LocalesResponse listLocales(projectId)

List locales with data

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { ListLocalesRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
  } satisfies ListLocalesRequest;

  try {
    const data = await api.listLocales(body);
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

### Return type

[**LocalesResponse**](LocalesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Locales |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listModels

> ModelsResponse listModels(projectId)

List models with data

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { ListModelsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
  } satisfies ListModelsRequest;

  try {
    const data = await api.listModels(body);
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

### Return type

[**ModelsResponse**](ModelsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Models |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listProjects

> ListProjects200Response listProjects(output)

List projects

All projects accessible with your API key.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { ListProjectsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // 'flat' | 'csv' | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \'flat\' returns the same metadata plus \'columns\' and \'rows\'; \'csv\' returns those rows as text/csv. Errors are always returned as JSON. (optional)
    output: output_example,
  } satisfies ListProjectsRequest;

  try {
    const data = await api.listProjects(body);
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
| **output** | `flat`, `csv` | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. \&#39;flat\&#39; returns the same metadata plus \&#39;columns\&#39; and \&#39;rows\&#39;; \&#39;csv\&#39; returns those rows as text/csv. Errors are always returned as JSON. | [Optional] [Defaults to `undefined`] [Enum: flat, csv] |

### Return type

[**ListProjects200Response**](ListProjects200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Projects |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateProject

> ProjectUpdateResponse updateProject(id, updateProjectRequest)

Update a project profile (Brand Book)

Updates the project name and profile, the same fields as Project Settings: name, brand_name, description, industry, business_model (plus business_model_other when it is OTHER), target_audience, brand_voice, goals, primary_products, matching_names, and the additional owned domains (additional_owned_domains). Send only the fields to change; unknown fields are rejected, and a request is applied whole or not at all. All seven Brand Book fields feed every GEO Writer task and prompt suggestions; only industry, description, and target_audience help Recommendations. A matching_names change re-runs mention/citation matching over the project history in the background, and an additional_owned_domains change reprocesses the past answers that cite an added or removed domain (rematching&#x3D;true); further edits are rejected while that runs. Only the account owner can send additional_owned_domains: a team member key gets ERR_INSUFFICIENT_PERMISSION and nothing is applied. prompt_limit sets or (null) removes the project\&#39;s own prompt cap, as in Account Settings &gt; Prompt Limits. Only the account owner or a co-owner whose permissions grant Projects update can send it (Account Settings &gt; Prompt Limits lets any co-owner change it; here a co-owner, like every team member, also needs Projects update): any other team member gets ERR_INSUFFICIENT_PERMISSION, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with nothing applied. A request that sends only prompt_limit is applied even while a rematch runs. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { UpdateProjectOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // number
    id: 56,
    // UpdateProjectRequest
    updateProjectRequest: ...,
  } satisfies UpdateProjectOperationRequest;

  try {
    const data = await api.updateProject(body);
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
| **updateProjectRequest** | [UpdateProjectRequest](UpdateProjectRequest.md) |  | |

### Return type

[**ProjectUpdateResponse**](ProjectUpdateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated |  -  |
| **403** | A write with a read-only key answers ERR_INSUFFICIENT_SCOPE. A team member whose permissions do not grant Projects update (a co-owner included), who sends additional_owned_domains, or who sends prompt_limit without being a co-owner answers ERR_INSUFFICIENT_PERMISSION. A key limited to some projects that sends prompt_limit answers ERR_KEY_PROJECT_SCOPED. All with the same status, and nothing in the request is applied |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateProjectDraft

> updateProjectDraft(id, updateProjectDraftRequest)

Submit a wizard step

Submit one step (details, prompts, competitors, owned_media). Strict forward gating: a step is only accepted when every previous step is complete (&#x60;ERR_DRAFT_STATE&#x60; otherwise); completed steps can be resubmitted. Responds with the updated draft plus AI suggestions for the next step.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@llmpulse/sdk';
import type { UpdateProjectDraftOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: id_example,
    // UpdateProjectDraftRequest
    updateProjectDraftRequest: ...,
  } satisfies UpdateProjectDraftOperationRequest;

  try {
    const data = await api.updateProjectDraft(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |
| **updateProjectDraftRequest** | [UpdateProjectDraftRequest](UpdateProjectDraftRequest.md) |  | |

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
| **200** | Draft envelope with next-step suggestions |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a key limited to some projects ERR_KEY_PROJECT_SCOPED, with the same status: this operation acts on the whole account |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

