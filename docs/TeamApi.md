# TeamApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTeamInvitation**](TeamApi.md#createteaminvitationoperation) | **POST** /team_invitations | Invite a team member |
| [**listTeamInvitations**](TeamApi.md#listteaminvitations) | **GET** /team_invitations | List pending team invitations |
| [**listTeamMembers**](TeamApi.md#listteammembers) | **GET** /team_members | List team members |
| [**removeTeamMember**](TeamApi.md#removeteammember) | **DELETE** /team_members/{id} | Remove a team member |
| [**revokeTeamInvitation**](TeamApi.md#revoketeaminvitation) | **DELETE** /team_invitations/{id} | Revoke a pending team invitation |



## createTeamInvitation

> CreateTeamInvitation201Response createTeamInvitation(createTeamInvitationRequest)

Invite a team member

Invites someone to the account team with the same rules as the Team Members settings page, and sends them the invitation email (email_sent is false when the email provider refused it; the invitation still exists, so revoke it and invite again once the address is fixed). Send project_ids, or all_projects: true for every project (for a team member inviting, every project they can access). The account owner and co-owners choose the access with permission_role: full_access (default), view_only, custom (with permissions, feature key to verbs) or account_role (with account_role_id). A team member with permission to invite cannot choose access: leave those fields out and the invitation copies their own permissions. Only the account owner can set account_admin (co-owner) or billing_access. An address already registered on the platform, or with an invitation pending, is refused with ERR_INVALID_PARAM (revoke the pending one first). An account that cannot add more team members, or that reached its daily limit of invitations sent through the API and MCP (revoked ones count), answers ERR_LIMIT_REACHED; the message says which. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  TeamApi,
} from '@llmpulse/sdk';
import type { CreateTeamInvitationOperationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TeamApi(config);

  const body = {
    // CreateTeamInvitationRequest
    createTeamInvitationRequest: ...,
  } satisfies CreateTeamInvitationOperationRequest;

  try {
    const data = await api.createTeamInvitation(body);
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
| **createTeamInvitationRequest** | [CreateTeamInvitationRequest](CreateTeamInvitationRequest.md) |  | |

### Return type

[**CreateTeamInvitation201Response**](CreateTeamInvitation201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. The invitation, as GET /team_invitations lists it, and whether the email went out. |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED, since the team belongs to the whole account. A team member without the Team Members permission, or asking for something only the owner or a co-owner can do, answers ERR_INSUFFICIENT_PERMISSION, and a write with a read-only key ERR_INSUFFICIENT_SCOPE, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTeamInvitations

> ListTeamInvitations200Response listTeamInvitations(page, perPage)

List pending team invitations

Lists invitations that have not been accepted yet: the address, the access and projects the person will get, when the invitation was sent and when its link expires. An accepted invitation keeps its id and moves to GET /team_members. Same access rules as GET /team_members.

### Example

```ts
import {
  Configuration,
  TeamApi,
} from '@llmpulse/sdk';
import type { ListTeamInvitationsRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TeamApi(config);

  const body = {
    // number (optional)
    page: 56,
    // number | Default 20, max 100 (optional)
    perPage: 56,
  } satisfies ListTeamInvitationsRequest;

  try {
    const data = await api.listTeamInvitations(body);
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
| **page** | `number` |  | [Optional] [Defaults to `undefined`] |
| **perPage** | `number` | Default 20, max 100 | [Optional] [Defaults to `undefined`] |

### Return type

[**ListTeamInvitations200Response**](ListTeamInvitations200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED, since the team belongs to the whole account. A team member without the Team Members permission, or asking for something only the owner or a co-owner can do, answers ERR_INSUFFICIENT_PERMISSION, and a write with a read-only key ERR_INSUFFICIENT_SCOPE, with the same status |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTeamMembers

> ListTeamMembers200Response listTeamMembers(page, perPage)

List team members

Lists the account owner first, then every team member who joined, with their access level (permission_role, account role and the resulting permissions), co-owner and billing flags, project access, status (active or blocked) and last sign-in. Pending invitations are listed by GET /team_invitations; GET /account limits.team_members.used counts both. Available to the account owner, co-owners and team members with the Team Members permission. A key limited to some projects answers ERR_KEY_PROJECT_SCOPED: the team belongs to the whole account.

### Example

```ts
import {
  Configuration,
  TeamApi,
} from '@llmpulse/sdk';
import type { ListTeamMembersRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TeamApi(config);

  const body = {
    // number (optional)
    page: 56,
    // number | Default 20, max 100 (optional)
    perPage: 56,
  } satisfies ListTeamMembersRequest;

  try {
    const data = await api.listTeamMembers(body);
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
| **page** | `number` |  | [Optional] [Defaults to `undefined`] |
| **perPage** | `number` | Default 20, max 100 | [Optional] [Defaults to `undefined`] |

### Return type

[**ListTeamMembers200Response**](ListTeamMembers200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED, since the team belongs to the whole account. A team member without the Team Members permission, or asking for something only the owner or a co-owner can do, answers ERR_INSUFFICIENT_PERMISSION, and a write with a read-only key ERR_INSUFFICIENT_SCOPE, with the same status |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## removeTeamMember

> RemoveTeamMember200Response removeTeamMember(id)

Remove a team member

Removes a member from the team, as the settings page does: their sessions and API keys stop working at once and their user account is deleted in the background shortly after. Account owner or co-owner only; a co-owner cannot remove the owner, another co-owner or themselves. The owner cannot be removed. Pending invitations are revoked with DELETE /team_invitations/{id}; an id that is not a member of the account answers ERR_NOT_FOUND. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  TeamApi,
} from '@llmpulse/sdk';
import type { RemoveTeamMemberRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TeamApi(config);

  const body = {
    // number | The member id from GET /team_members
    id: 56,
  } satisfies RemoveTeamMemberRequest;

  try {
    const data = await api.removeTeamMember(body);
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
| **id** | `number` | The member id from GET /team_members | [Defaults to `undefined`] |

### Return type

[**RemoveTeamMember200Response**](RemoveTeamMember200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED, since the team belongs to the whole account. A team member without the Team Members permission, or asking for something only the owner or a co-owner can do, answers ERR_INSUFFICIENT_PERMISSION, and a write with a read-only key ERR_INSUFFICIENT_SCOPE, with the same status |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeTeamInvitation

> RevokeTeamInvitation200Response revokeTeamInvitation(id)

Revoke a pending team invitation

Revokes a pending invitation: its link stops working immediately. Account owner or co-owner only, and a co-owner cannot revoke an invitation that makes someone a co-owner. Members who already joined are removed with DELETE /team_members/{id}; an id that is not a pending invitation of the account answers ERR_NOT_FOUND. Requires a &#x60;read_write&#x60; scope API key.

### Example

```ts
import {
  Configuration,
  TeamApi,
} from '@llmpulse/sdk';
import type { RevokeTeamInvitationRequest } from '@llmpulse/sdk';

async function example() {
  console.log("🚀 Testing @llmpulse/sdk SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: BearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TeamApi(config);

  const body = {
    // number | The invitation id from GET /team_invitations
    id: 56,
  } satisfies RevokeTeamInvitationRequest;

  try {
    const data = await api.revokeTeamInvitation(body);
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
| **id** | `number` | The invitation id from GET /team_invitations | [Defaults to `undefined`] |

### Return type

[**RevokeTeamInvitation200Response**](RevokeTeamInvitation200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED, since the team belongs to the whole account. A team member without the Team Members permission, or asking for something only the owner or a co-owner can do, answers ERR_INSUFFICIENT_PERMISSION, and a write with a read-only key ERR_INSUFFICIENT_SCOPE, with the same status |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

