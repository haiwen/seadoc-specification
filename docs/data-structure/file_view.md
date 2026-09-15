# File view

`file_view` is a block-level void element that embeds a file view. It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Required properties

- `data` (required, object): file-view data. This specification defines the fields below. Other implementation-specific fields may exist but are outside the current documented contract.
- `data.wiki_id` (required, string): containing wiki identifier.
- `data.file_view_id` (required, string): file-view identifier.

## Optional properties
- `data.height` (optional, number): saved display height.

```json
{
  "id": "file-view-id",
  "type": "file_view",
  "data": {
    "wiki_id": "wiki-id",
    "file_view_id": "file-view-id",
    "height": 300
  },
  "children": [
    {
      "id": "file-view-placeholder-id",
      "text": ""
    }
  ]
}
```
