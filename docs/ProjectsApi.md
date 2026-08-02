# ProjectsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createProject**](ProjectsApi.md#createproject) | **POST** /projects | Create a project (fast mode) |
| [**createProjectDraft**](ProjectsApi.md#createprojectdraftoperation) | **POST** /project_drafts | Start a project draft (wizard step 1) |
| [**finalizeProjectDraft**](ProjectsApi.md#finalizeprojectdraftoperation) | **POST** /project_drafts/{id}/finalize | Finalize a draft into a real project |
| [**getProjectDraft**](ProjectsApi.md#getprojectdraft) | **GET** /project_drafts/{id} | Read a project draft |
| [**updateProjectDraft**](ProjectsApi.md#updateprojectdraftoperation) | **PATCH** /project_drafts/{id} | Submit a wizard step |



## createProject

> ProjectCreateResponse createProject(projectCreateRequest)

Create a project (fast mode)

Create a complete project in one call: project fields, prompts (queued for execution and categorization), competitors, weekly email subscription. Idempotent via &#x60;external_identifier&#x60; (embed-enabled accounts only; replay returns 200 with the existing project). Requires a &#x60;read_write&#x60; scope API key.

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
| **403** | API key lacks write permission |  -  |
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
| **403** | API key lacks write permission |  -  |

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
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

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
| **404** | Resource not found |  -  |

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
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

