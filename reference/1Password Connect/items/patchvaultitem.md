---
title: Update a subset of Item attributes
excerpt: >
  Applies a modified [RFC6902 JSON Patch](https://tools.ietf.org/html/rfc6902)
  document to an Item or ItemField. This endpoint only supports `add`, `remove`
  and `replace` operations.


  When modifying a specific ItemField, the ItemField's ID in the `path`
  attribute of the operation object: `/fields/{fieldId}`
api:
  file: spyfu_api.json
  operationId: PatchVaultItem
hidden: false
---