# Text

## Node Structure

A text leaf has:

- `id` (required, string): unique node identifier.
- `text` (required, string): displayed text.

Text leaves do not require `type` or `children`. For example:

```json
{
  "id": "text-id",
  "text": "Text content"
}
```

## Text Formatting (Marks)

Text leaves may carry the following formatting fields:

- `bold`, `italic`, `underline`, `strikethrough`, `superscript`, `subscript`, and `code` (optional, boolean).
- `color` and `highlight_color` (optional, string).
- `font_size` (optional, number).
- `font` (optional, string).

Revision, diff, comment, selection, cursor, AI, and syntax-decoration fields are not ordinary rich-text formatting fields in this specification.
