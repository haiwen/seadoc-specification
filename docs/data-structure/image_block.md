# Image Block { #image_block }

`image_block` is a non-void block element node that displays one inline [image](image.md) on its own line.

## Usage and Children

- `image_block` normally appears in the document's top-level `elements` list. Inserting a single image into an empty top-level paragraph creates this block.
- Its `children` contain one inline [image](image.md), with [text leaves](text.md) before and after it for cursor placement. These leaves can be empty; consumers must not require an `image_block` to contain only one child.
- Inside a blockquote, callout, or column, the normal insertion command keeps the image inline within a paragraph.
- The editor converts an `image_block` containing multiple images into a paragraph.

## Data Structure

`image_block` uses the [common element fields](../support-types.md#element-nodes). Image source and link settings belong to its child [Image](image.md#properties).

### Image Block Example

```json
{
  "id": "image-block-id",
  "type": "image_block",
  "children": [
    {
      "id": "before-image-id",
      "text": ""
    },
    {
      "id": "image-id",
      "type": "image",
      "data": {
        "src": "/image.png"
      },
      "children": [
        {
          "id": "image-placeholder-id",
          "text": ""
        }
      ]
    },
    {
      "id": "after-image-id",
      "text": ""
    }
  ]
}
```
