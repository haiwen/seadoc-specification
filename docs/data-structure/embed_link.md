# Embed link

`embed_link` is a block-level void element that embeds an external service. It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Required properties

- `link` (required, string): embedded URL.
- `link_type` (required, string): embed provider. Current values are `seatable` and `figma`.

## Optional properties
- `data.height` (optional, number): saved display height.

```json
{
  "id": "embed-link-id",
  "type": "embed_link",
  "link": "https://www.figma.com/file/example",
  "link_type": "figma",
  "data": {
    "height": 400
  },
  "children": [
    {
      "id": "embed-link-placeholder-id",
      "text": ""
    }
  ]
}
```
