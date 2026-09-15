# Sdoc_link

`sdoc_link` is an inline void element that references another SeaDoc file. It normally appears in a [paragraph](paragraph.md). It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Properties

- `doc_uuid` (required, string): referenced SeaDoc file identifier.
- `title` (required, string): display title.
- `display_type` (required, string): display mode.

```json
{
  "id": "sdoc-link-id",
  "type": "sdoc_link",
  "doc_uuid": "c24cee20-88c2-4dba-beb9-4032c5e2c3e1",
  "title": "Project plan",
  "display_type": "text_link",
  "children": [
    {
      "id": "sdoc-link-text-id",
      "text": "Project plan"
    }
  ]
}
```

## Compatibility

Historical documents may retain the `.sdoc` suffix in `title` and displayed text. New documents use the suffix-free display form. Compatibility and migration behavior may depend on the reader implementation.
