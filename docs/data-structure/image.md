# Image

Image-related nodes are `image` and `image_block`.

## Image

`image` is an inline void element. It normally appears in a [paragraph](paragraph.md) or another text container. It follows the [void element](../support-types.md#void-elements) placeholder rule.

### Properties

- `data` (required, object): image data.
- `data.src` (required, string): image source.
- `data.href` (optional, string): link target for the image.
- `data.linked_wiki_id` (optional, string): target wiki ID for a wiki-page image link.
- `data.linked_wiki_page_id` (optional, string): target wiki page ID for a wiki-page image link.

```json
{
  "id": "image-id",
  "type": "image",
  "data": {
    "src": "/image.png",
    "href": "https://cloud.example.com/wikis/wiki-id/page-id/",
    "linked_wiki_id": "wiki-id",
    "linked_wiki_page_id": "page-id"
  },
  "children": [
    {
      "id": "image-placeholder-id",
      "text": ""
    }
  ]
}
```

## Image_block

`image_block` is a block-level wrapper for an inline `image`. Its children may include empty text leaves before or after the image as structural placeholders. Consumers must not require an `image_block` to contain only one child.

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
