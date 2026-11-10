# SeaDoc Document Model

This page describes the SeaDoc document format, node hierarchy, and content element types. Follow the links to individual node pages for detailed data structures.

## Document Format

SeaDoc documents stored on disk use `format_version: 4` and have the following structure:

```json
{
  "version": 1,
  "format_version": 4,
  "elements": [],
  "last_modify_user": "user@example.com"
}
```

All four fields are required:

- `version`: document revision number.
- `format_version`: document format version, currently `4`.
- `elements`: list of top-level element nodes.
- `last_modify_user`: last modifying user, or an empty string when no user is available.

`cursors` belongs to runtime collaboration responses and is not stored in the `.sdoc` file.

## Node Structure

A SeaDoc document is a tree with three node categories:

1. **Document root**: the document itself, containing top-level element nodes in its `elements` property.
2. **Element nodes**: containers holding other element nodes or text nodes in their `children` property.
3. **Text nodes**: leaf nodes containing text content and optional formatting marks.

Every element and text node requires a non-empty string `id` that is unique within the document. Consumers must not require a particular UUID or slug format.

### Element Nodes

Element nodes can be block elements, which form separate blocks of content, or inline elements, which flow with text inside a block. Both groups include non-void and void elements.

#### Non-Void Elements

An element node normally has:

- `id` (required, string): unique node identifier.
- `type` (required, string): element type.
- `children` (required, array): child nodes.

Element-specific fields, including any `data` object, are documented on the corresponding [element pages](#element-types).

Non-void elements expose their child content for editing. Examples include:

- **Block elements**: [`paragraph`](data-structure/paragraph.md) and [`blockquote`](data-structure/blockquote.md).
- **Inline elements**: [`link`](data-structure/link.md).

#### Void Elements

Void elements are treated as a single unit rather than exposing their children as editable text. Examples include:

- **Block elements**: [`divider`](data-structure/divider.md) and [`formula`](data-structure/formula.md).
- **Inline elements**: [`image`](data-structure/image.md) and [`sdoc_link`](data-structure/sdoc_link.md).

Block and inline void elements still have `children`. Most, including block void elements and inline images, contain an empty text leaf as a structural placeholder, with visible content stored in element properties. File links and SeaDoc links can retain their display names in text children. Those stored labels are not editable child content; void elements do not require every persisted text child to be empty.

For example, a [`divider`](data-structure/divider.md) has the following structure:

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

### Text Nodes

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

See [Text](data-structure/text.md) for the full text node documentation, including supported [formatting marks](data-structure/text.md#text-formatting-marks).

## Element Types

### Content Elements

The following content element types are named in this specification release. Existing SeaDoc implementations may accept additional types. Each link leads to the corresponding data structure; some types share a page.

1. [`blockquote`](data-structure/blockquote.md)
2. [`callout`](data-structure/callout.md)
3. [`check_list_item`](data-structure/check_list_item.md)
4. [`code_block`](data-structure/code_block.md)
5. [`divider`](data-structure/divider.md)
6. [`embed_link`](data-structure/embed_link.md)
7. [`file_link`](data-structure/file_link.md)
8. [`formula`](data-structure/formula.md)
9. [`header1` through `header6`](data-structure/header.md)
10. [`image`](data-structure/image.md#image)
11. [`image_block`](data-structure/image.md#image_block)
12. [`link`](data-structure/link.md)
13. [`multi_column`](data-structure/multi_column.md)
14. [`ordered_list`](data-structure/list.md#ordered_list-nodes)
15. [`paragraph`](data-structure/paragraph.md)
16. [`sdoc_link`](data-structure/sdoc_link.md)
17. [`subtitle`](data-structure/header.md)
18. [`table`](data-structure/table.md)
19. [`title`](data-structure/header.md)
20. [`unordered_list`](data-structure/list.md#unordered_list-nodes)
21. [`video`](data-structure/video.md)
22. [`whiteboard`](data-structure/whiteboard.md)
