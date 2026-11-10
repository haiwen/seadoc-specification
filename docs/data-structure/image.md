# Image

`image` is an inline element node that represents an image. It is a void element. For an image displayed on its own line, see [Image Block](image_block.md).

## Usage and Children

- `image` appears inside a text block such as a [paragraph](paragraph.md) or [table cell](table.md), or inside an [image block](image_block.md). It does not appear directly in the document's `elements` list.
- Its `children` contain one empty [text node](text.md) as a structural placeholder. The image source and link settings belong in `data`; see [Void Elements](../support-types.md#void-elements).
- The normal insertion command does not insert images inside headings, titles, subtitles, list items, checklist items, or code content.

## Data Structure

### Properties

The `image` element has:

- `data` (required, object): image data.
- `data.src` (required, string): non-empty image source, commonly a document asset path such as `/image.png` or an absolute image URL. Asset paths are resolved using the reader's document asset context; they are not necessarily paths relative to the documentation site.
- `data.file_uuid` (optional, string): associated image file identifier.
- `data.href` (optional, string): absolute HTTP(S) link target for the image. An absent field or an empty string means the image has no hyperlink.
- `data.linked_wiki_id` (optional, string): target wiki ID for a wiki-page image link.
- `data.linked_wiki_page_id` (optional, string): target wiki page ID for a wiki-page image link.

### Inline Image Example

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
