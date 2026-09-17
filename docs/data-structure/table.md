# Table

`table` is a block element with the following structural hierarchy:

```text
table -> table_row -> table_cell
```

`table_row` and `table_cell` are structural element types. They are not independent top-level content elements. Newly-created cells typically contain text leaves or inline content.

## Editor-created defaults

A newly-created rectangular table has these layout fields:

- `columns` (required for newly-created tables, array): column width metadata. Each item has `width`.
- `ui` (required for newly-created tables, object): table display metadata such as `alternate_highlight`.
- `style.gridTemplateColumns` (required for newly-created tables, string): CSS grid column layout.
- `style.gridAutoRows` (required for newly-created tables, string): CSS grid row layout.
- `table_row.style.min_height` (required for newly-created rows, number): row minimum height.
- `table_cell.style` (required for newly-created cells, object): cell style.
- `table_cell.inherit_style` (required for newly-created cells, object): style inherited by inserted cells.

New table cells use `style.align_items` for vertical alignment.

```json
{
  "id": "table-id",
  "type": "table",
  "columns": [
    { "width": 336 },
    { "width": 336 }
  ],
  "ui": {
    "alternate_highlight": false
  },
  "style": {
    "gridTemplateColumns": "repeat(2, 336px)",
    "gridAutoRows": "minmax(42px, auto)"
  },
  "children": [
    {
      "id": "row-id",
      "type": "table_row",
      "style": {
        "min_height": 42
      },
      "children": [
        {
          "id": "cell-id",
          "type": "table_cell",
          "style": {
            "text_align": "left",
            "align_items": "center",
            "background_color": ""
          },
          "inherit_style": {
            "text_align": "left",
            "background_color": ""
          },
          "children": [
            {
              "id": "cell-text-id",
              "text": "Name"
            }
          ]
        }
      ]
    }
  ]
}
```

## Compatibility

Historical documents may contain `style.alignItems`. New documents use `style.align_items`. Compatibility and migration behavior may depend on the reader implementation.
