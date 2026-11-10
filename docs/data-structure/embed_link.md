# Embed Link

`embed_link` is a block element node that embeds content from an external service, such as SeaTable or Figma. It is a void element.

## Usage and Children

- It normally appears as a standalone block in the document's `elements` list.
- Its `children` contain one empty [text node](text.md) as a structural placeholder. The embedded content is identified by `link` and `link_type`, rather than editable child text. See [Void Elements](../support-types.md#void-elements).

## Data Structure

### Required Properties

- `link` (required, string): non-empty, absolute HTTP(S) URL of the embedded resource.
- `link_type` (required, string): embed provider. Current values are `seatable` and `figma`.

### Optional Properties

- `data` (optional, object): saved display settings. It can be omitted when no height is saved.
- `data.height` (optional, number): positive, finite display height in CSS pixels (`px`), without a unit suffix in JSON. When omitted, the editor uses `300px`.

The editor clamps positive saved heights to `300`–`550` pixels for display and saves resized heights within that range. Non-positive saved heights fall back to `300px`. This display behavior does not require older saved values to already fall within the resize range.

### Example

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
