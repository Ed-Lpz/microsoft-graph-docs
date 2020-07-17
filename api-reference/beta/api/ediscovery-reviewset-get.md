---
title: "Get reviewSet"
description: "Retrieve the properties and relationships of reviewSet object."
localization_priority: Normal
author: "mahage-msft"
ms.prod: "compliance"
doc_type: "apiPageType"
---

# Get reviewSet

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of a [reviewSet](../resources/ediscoveryreviewset.md) object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | User.Read |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Not supported. |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /compliance/ediscovery/cases/{id}/reviewSets/{id}
```

## Optional query parameters

This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

By default, all review set fields are returned, however, you can specify certain fields to return using the OData `$select` query parameter.  For example, to only return the **displayName** & Id, add the following to your query `$select=displayName,Id`.

Since a request may return many cases which are not of interest, they can be filtered with **displayName**.  To filter by **displayName**, add the following to your query `$filter=displayName eq 'rs1'` where the review set name is rs1.

For more information about filtering and specifying fields, see [Using Filter Expressions in OData URIs
](https://docs.microsoft.com/dynamics-nav/using-filter-expressions-in-odata-uris)

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {token} |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and the requested [reviewSet](../resources/ediscoveryreviewset.md) object in the response body.

## Examples

### Request

The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "ediscovery-reviewset-get"
}-->

```http
GET https://graph.microsoft.com/beta/compliance/ediscovery/cases('6f65a8e4-c6a0-4cff-8a81-c9ab5df7290d')/reviewSets('0157910c-57ce-4e48-bd4b-90f3c88ca32e')
```

### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.reviewSet"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/compliance/ediscovery/$metadata#cases('6f65a8e4-c6a0-4cff-8a81-c9ab5df7290d')/reviewSets/$entity",
    "id": "0157910c-57ce-4e48-bd4b-90f3c88ca32e",
    "displayName": "My Reviewset 3",
    "createdBy": {
        "user": {
            "id": "efee1b77-fb3b-4f65-99d6-274c11914d12",
            "displayName": "eDiscovery admin"
        }
    },
    "createdDateTime": "2020-03-11T08:40:14.9486058Z"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get reviewSet",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->