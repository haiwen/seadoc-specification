# SeaDoc Link { #sdoc_link }

`sdoc_link` is an inline element node that references another SeaDoc file. It is a void element.

## Children

- Its `children` contain a [text node](text.md) storing the display name. The editor treats the link as a single unit; the stored display name is not ordinary editable child text.

## Data Structure

### Properties

- `doc_uuid` (required, string): referenced SeaDoc file identifier.
- `title` (required, string): display title.
- `display_type` (required, string): one of `text_link` (display name only), `icon_link` (file icon and display name), or `card_link` (document card). The insertion command creates `icon_link` by default.

Writers must persist one of these three display modes. For compatibility, a missing or empty `display_type` is displayed as a text link by the editor; this fallback is different from the insertion default.

### Example

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

### Compatibility

Historical documents may retain the `.sdoc` suffix in `title` and displayed text. New documents use the suffix-free display form. Compatibility and migration behavior may depend on the reader implementation.
