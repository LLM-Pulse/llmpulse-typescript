# AnnotationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAnnotation**](AnnotationsApi.md#createannotationoperation) | **POST** /annotations | Create a timeline annotation |
| [**deleteAnnotation**](AnnotationsApi.md#deleteannotation) | **DELETE** /annotations/{id} | Delete a timeline annotation |
| [**listAnnotations**](AnnotationsApi.md#listannotations) | **GET** /annotations | List timeline annotations |
| [**updateAnnotation**](AnnotationsApi.md#updateannotationoperation) | **PATCH** /annotations/{id} | Update a timeline annotation |



## createAnnotation

> createAnnotation(createAnnotationRequest)

Create a timeline annotation

Marks a date in the project timeseries with a title + description. Available on every plan. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  AnnotationsApi,
} from '@llmpulse/sdk';
import type { CreateAnnotationOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AnnotationsApi(config);

  const body = {
    // CreateAnnotationRequest
    createAnnotationRequest: ...,
  } satisfies CreateAnnotationOperationRequest;

  try {
    const data = await api.createAnnotation(body);
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
| **createAnnotationRequest** | [CreateAnnotationRequest](CreateAnnotationRequest.md) |  | |

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


## deleteAnnotation

> deleteAnnotation(projectId, id)

Delete a timeline annotation

Deletes an annotation. Same ownership rule as PATCH. Available on every plan and requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  AnnotationsApi,
} from '@llmpulse/sdk';
import type { DeleteAnnotationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AnnotationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // number
    id: 56,
  } satisfies DeleteAnnotationRequest;

  try {
    const data = await api.deleteAnnotation(body);
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
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAnnotations

> listAnnotations(projectId, from, to, annotationCategoryId, page, perPage)

List timeline annotations

Lists project timeline annotations, newest first. Rows can come from manual notes, project automations, GEO tests, or platform events. The origin field distinguishes them; editable says whether the requesting user may modify the row. Available on every plan.

### Example

```ts
import {
  Configuration,
  AnnotationsApi,
} from '@llmpulse/sdk';
import type { ListAnnotationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AnnotationsApi(config);

  const body = {
    // number | Project ID
    projectId: 56,
    // Date (optional)
    from: 2013-10-20,
    // Date (optional)
    to: 2013-10-20,
    // number (optional)
    annotationCategoryId: 56,
    // number (optional)
    page: 56,
    // number (optional)
    perPage: 56,
  } satisfies ListAnnotationsRequest;

  try {
    const data = await api.listAnnotations(body);
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
| **from** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **to** | `Date` |  | [Optional] [Defaults to `undefined`] |
| **annotationCategoryId** | `number` |  | [Optional] [Defaults to `undefined`] |
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
| **200** | Paginated annotations |  -  |
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAnnotation

> updateAnnotation(id, updateAnnotationRequest)

Update a timeline annotation

Updates title, description, annotation_date, color and/or annotation_category_id. Only user-created annotations belonging to the requesting user can be updated (system annotations never). Available on every plan and requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  AnnotationsApi,
} from '@llmpulse/sdk';
import type { UpdateAnnotationOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AnnotationsApi(config);

  const body = {
    // number
    id: 56,
    // UpdateAnnotationRequest
    updateAnnotationRequest: ...,
  } satisfies UpdateAnnotationOperationRequest;

  try {
    const data = await api.updateAnnotation(body);
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
| **updateAnnotationRequest** | [UpdateAnnotationRequest](UpdateAnnotationRequest.md) |  | |

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
| **403** | API key belongs to a team member whose permission matrix does not grant this feature |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

