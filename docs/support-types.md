# SeaDoc support node types

## Document format

SeaDoc documents stored on disk use `format_version: 4`. The persisted document envelope is:

```json
{
  "version": 1,
  "format_version": 4,
  "elements": [],
  "last_modify_user": "user@example.com"
}
```

- `version` is required and records the document revision number.
- `format_version` is required and is `4` for the current on-disk format.
- `elements` is required and contains the top-level element nodes.
- `last_modify_user` is required and records the last modifying user. It may be an empty string when no user is available.

`cursors` is runtime collaboration response state. It is not part of the on-disk `.sdoc` format.

## Nodes

Every node `id` is a required, non-empty string that is unique within its document. Consumers must not require a particular UUID or slug format.

### Element nodes

An element node normally has:

- `id` (required, string): unique node identifier.
- `type` (required, string): element type.
- `children` (required, array): child nodes.

Some elements have additional fields or a `data` object. See the page for that element type.

### Text leaves

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

### Void elements

A void element stores its user-visible content in element properties rather than editable text. It still has `children`. The empty text leaf in `children` is a structural placeholder, not user content. Void does not mean the element has no `children`.

```json
{
  "id": "element-id",
  "type": "divider",
  "children": [
    {
      "id": "placeholder-id",
      "text": ""
    }
  ]
}
```

### Rich-text marks

Text leaves may carry the following formatting fields:

- `bold`, `italic`, `underline`, `strikethrough`, `superscript`, `subscript`, and `code` (optional, boolean).
- `color` and `highlight_color` (optional, string).
- `font_size` (optional, number).
- `font` (optional, string).

Revision, diff, comment, selection, cursor, AI, and syntax-decoration fields are not ordinary rich-text formatting fields in this specification.

## Node types

### Content element types

The following element types are named in this specification release. This list is not a complete inventory of every element accepted by existing SeaDoc implementations. A name in this list does not mean the type has a dedicated structure page.

1. blockquote
2. callout
3. check_list_item
4. code_block
5. divider
6. embed_link
7. file_link
8. file_view
9. formula
10. header1 through header6
11. image
12. image_block
13. link
14. mention
15. multi_column
16. ordered_list
17. paragraph
18. sdoc_link
19. subtitle
20. table
21. title
22. toggle_header
23. unordered_list
24. video
25. whiteboard

### Structural element types

The following types occur only as children of their owning content element:

- `code_line` within `code_block`.
- `table_row` within `table`.
- `table_cell` within `table_row`.
- `column` within `multi_column`.
- `toggle_header1`, `toggle_header2`, and `toggle_header3` within `toggle_header`.
- `toggle_content` within an expanded `toggle_header`.
