# File Link { #file_link }

`file_link` is an inline element node that references a non-SeaDoc file, such as a `.md` or `.txt` file. It is a void element.

## Children

- Its `children` contain a [text node](text.md) storing the filename. The editor treats the link as a single unit; the stored filename is not ordinary editable child text.

## Data Structure

### Properties

- `doc_uuid` (required, string): referenced file identifier.
- `title` (required, string): filename.
- `display_type` (required, string): one of `text_link` (filename only), `icon_link` (file icon and filename), or `card_link` (file card). The insertion command creates `icon_link` by default.

Writers must persist one of these three display modes. For compatibility, a missing or empty `display_type` is displayed as a text link by the editor; this fallback is different from the insertion default.

### Example

```json
{
  "id": "afLKcmNdR4ii2ZqvH8PP8w",
  "type": "file_link",
  "doc_uuid": "c24cee20-88c2-4dba-beb9-4032c5e2c3e1",
  "title": "aaa.txt",
  "display_type": "text_link",
  "children": [
    {
      "id": "bKfw6ms4QlqUf1J5aFCr4w",
      "text": "aaa.txt"
    }
  ]
}
```
