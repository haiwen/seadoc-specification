# Multi Column

`multi_column` is a block element node that arranges document content into columns.

## Children

- Its direct `children` are `column` structural elements.
- A column contains block content, including [paragraphs](paragraph.md) and supported nested blocks such as [blockquotes](blockquote.md), [callouts](callout.md), [lists](list.md), and [code blocks](code_block.md).
- A new column starts with a paragraph containing an empty text node. Text and inline elements belong inside its child blocks.

## Data Structure

### Editor-Created Defaults

- `column` (required for newly-created layouts, array): ordered column metadata.
- `style.gridTemplateColumns` (required for newly-created layouts, string): CSS grid column track list, such as `repeat(2, 300px)` or `250px 350px`. This CSS string includes length units.

Each `column` metadata item has:

- `key` (required, string): non-empty identifier matching its child column's `id`.
- `width` (required, number): positive, finite width in CSS pixels (`px`), without a unit suffix in JSON.
- `left` (optional, number): non-negative, finite horizontal layout metadata in CSS pixels (`px`). Readers can derive column positions from the ordered widths without requiring this field.

Initial widths depend on the available layout width and column count. Historical layouts may use other positive widths.

Each child `column` has:

- `id` (required, string): normally corresponding to the metadata `key`.
- `type` (required): `column`.
- `width` (required for newly-created columns, number): positive, finite width in CSS pixels (`px`), without a unit suffix in JSON. The editor initializes it from the parent column metadata and prefers the matching metadata width when rendering after layout changes.
- `children` (required, array): block content. A new column begins with a paragraph and text leaf.

### Example

```json
{
  "id": "multi-column-id",
  "type": "multi_column",
  "column": [
    {
      "key": "column-one-id",
      "width": 300,
      "left": 0
    },
    {
      "key": "column-two-id",
      "width": 300,
      "left": 300
    }
  ],
  "style": {
    "gridTemplateColumns": "repeat(2, 300px)"
  },
  "children": [
    {
      "id": "column-one-id",
      "type": "column",
      "width": 300,
      "children": [
        {
          "id": "paragraph-one-id",
          "type": "paragraph",
          "children": [
            {
              "id": "text-one-id",
              "text": "Column one content"
            }
          ]
        }
      ]
    },
    {
      "id": "column-two-id",
      "type": "column",
      "width": 300,
      "children": [
        {
          "id": "paragraph-two-id",
          "type": "paragraph",
          "children": [
            {
              "id": "text-two-id",
              "text": "Column two content"
            }
          ]
        }
      ]
    }
  ]
}
```
