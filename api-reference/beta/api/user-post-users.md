---
title: "Create user"
description: "Create a new user."
author: "yyuank"
ms.localizationpriority: medium
ms.prod: "users"
doc_type: apiPageType
---

# Create user

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [user](../resources/user.md).
The request body contains the user to create. At a minimum, you must specify the required properties for the user. You can optionally specify any other writable properties.

This operation returns by default only a subset of the properties for each user. These default properties are noted in the [Properties](../resources/user.md#properties) section. To get properties that are not returned by default, do a [GET operation](user-get.md) and specify the properties in a `$select` OData query option.

>[!NOTE]
>To create external users, use the [invitation API](invitation-post.md).

[!INCLUDE [national-cloud-support](../../includes/all-clouds.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "ignored", "name": "user_post_users" } -->
[!INCLUDE [permissions-table](../includes/permissions/user-post-users-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /users
```
## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |
| Content-Type  | application/json  |

## Request body

In the request body, supply a JSON representation of [user](../resources/user.md) object.

The following table lists the properties that are required when you create a user. If you're including an **identities** property for the user you're creating, not all the properties listed are required. For a [B2C local account identity](../resources/objectidentity.md), only  **passwordProfile** is required, and **passwordPolicies** must be set to `DisablePasswordExpiration`. For a social identity, none of the properties are required.

| Parameter | Type | Description|
|:---------------|:--------|:----------|
|accountEnabled |Boolean |True if the account is enabled; otherwise, false.|
|displayName |string |The name to display in the address book for the user.|
|onPremisesImmutableId |string |Only needs to be specified when creating a new user account if you are using a federated domain for the user's userPrincipalName (UPN) property.|
|mailNickname |string |The mail alias for the user.|
|passwordProfile|[PasswordProfile](../resources/passwordprofile.md) |The password profile for the user.|
|userPrincipalName |string |The user principal name (someuser@contoso.com). It's an Internet-style login name for the user based on the Internet standard RFC 822. By convention, this should map to the user's email name. The general format is alias@domain, where domain must be present in the tenant's collection of verified domains. The verified domains for the tenant can be accessed from the **verifiedDomains** property of [organization](../resources/organization.md). <br>NOTE: This property cannot contain accent characters. Only the following characters are allowed `A - Z`, `a - z`, `0 - 9`, ` ' . - _ ! # ^ ~`. For the complete list of allowed characters, see [username policies](/azure/active-directory/authentication/concept-sspr-policy#userprincipalname-policies-that-apply-to-all-user-accounts).|

Because the **user** resource supports [extensions](/graph/extensibility-overview), you can use the `POST` operation and add custom properties with your own data to the user instance while creating it.

Federated users created via this API will be forced to sign in every 12 hours by default. For information about how to change this, see [Exceptions for token lifetimes](/azure/active-directory/develop/active-directory-configurable-token-lifetimes#exceptions).

>[!NOTE]
>Adding a [B2C local account](../resources/objectidentity.md) to an existing **user** object is not allowed, unless the **user** object already contains a local account identity.

## Response

If successful, this method returns a `201 Created` response code and a [user](../resources/user.md) object in the response body.

## Example

### Example 1: Create a user

#### Request
Here is an example of the request.

# [HTTP](#tab/http)
<!-- {	
  "blockType": "request",	
  "name": "create_user_from_users_2"	
}-->

```http
POST https://graph.microsoft.com/beta/users
Content-type: application/json

{
  "accountEnabled": true,
  "displayName": "Adele Vance",
  "mailNickname": "AdeleV",
  "userPrincipalName": "AdeleV@contoso.onmicrosoft.com",
  "passwordProfile" : {
    "forceChangePasswordNextSignIn": true,
    "password": "xWwvJ]6NMw+bWH-d"
  }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-user-from-users-2-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-user-from-users-2-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-user-from-users-2-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-user-from-users-2-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-user-from-users-2-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-user-from-users-2-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-user-from-users-2-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/create-user-from-users-2-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

In the request body, supply a JSON representation of [user](../resources/user.md) object.
##### Response
Here is an example of the response. 

>[!NOTE]
>The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user"
} -->
```http
HTTP/1.1 201 Created
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#users/$entity",
    "id": "87d349ed-44d7-43e1-9a83-5f2406dee5bd",
    "businessPhones": [],
    "displayName": "Adele Vance",
    "givenName": "Adele",
    "jobTitle": "Product Marketing Manager",
    "mail": "AdeleV@contoso.onmicrosoft.com",
    "mobilePhone": "+1 425 555 0109",
    "officeLocation": "18/2111",
    "preferredLanguage": "en-US",
    "surname": "Vance",
    "userPrincipalName": "AdeleV@contoso.onmicrosoft.com"
}
```

### Example 2: Create a user with social and local account identities

Create a new user, with a local account identity with a sign-in name, an email address as sign-in, and with a social identity. This example is typically used for migration scenarios in B2C tenants.  

>[!NOTE] 
>For local account identities, password expirations must be disabled, and force change password at next sign-in must also be disabled.

#### Request


# [HTTP](#tab/http)
<!-- {	
  "blockType": "request",	
  "name": "create_user_from_users_identities"	
}-->

```http
POST https://graph.microsoft.com/beta/users
Content-type: application/json

{
  "displayName": "John Smith",
  "identities": [
    {
      "signInType": "userName",
      "issuer": "contoso.onmicrosoft.com",
      "issuerAssignedId": "johnsmith"
    },
    {
      "signInType": "emailAddress",
      "issuer": "contoso.onmicrosoft.com",
      "issuerAssignedId": "jsmith@yahoo.com"
    },
    {
      "signInType": "federated",
      "issuer": "facebook.com",
      "issuerAssignedId": "5eecb0cd"
    }
  ],
  "passwordProfile" : {
    "password": "password-value",
    "forceChangePasswordNextSignIn": false
  },
  "passwordPolicies": "DisablePasswordExpiration"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-user-from-users-identities-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-user-from-users-identities-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-user-from-users-identities-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-user-from-users-identities-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-user-from-users-identities-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-user-from-users-identities-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-user-from-users-identities-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/create-user-from-users-identities-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

Here is an example of the response. 

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user",
} -->
```http
HTTP/1.1 201 Created
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users/$entity",
  "displayName": "John Smith",
  "id": "4c7be08b-361f-41a8-b1ef-1712f7a3dfb2",
  "identities": [
    {
      "signInType": "userName",
      "issuer": "contoso.onmicrosoft.com",
      "issuerAssignedId": "johnsmith"
    },
    {
      "signInType": "emailAddress",
      "issuer": "contoso.onmicrosoft.com",
      "issuerAssignedId": "jsmith@yahoo.com"
    },
    {
      "signInType": "federated",
      "issuer": "facebook.com",
      "issuerAssignedId": "5eecb0cd"
    }
  ],
  "passwordPolicies": "DisablePasswordExpiration"
}
```

## See also

- [Add custom data to resources using extensions](/graph/extensibility-overview)
- [Add custom data to users using open extensions (preview)](/graph/extensibility-open-users)
- [Add custom data to groups using schema extensions (preview)](/graph/extensibility-schema-groups)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Create User",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
