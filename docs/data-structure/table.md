# Table

`table` is a block element node that represents content arranged into rows and cells.

## Usage and Children

- Its direct `children` are `table_row` elements, whose children are `table_cell` elements.
- Cells directly contain [text nodes](text.md) and supported inline elements, such as [links](link.md) and [images](image.md#image). A paragraph wrapper is not required; the editor flattens paragraph children when importing cells.

```text
table -> table_row -> table_cell -> text or inline elements
```

`table_row` and `table_cell` are structural element types.

## Data Structure

### Editor-Created Defaults

A newly-created rectangular table has these layout fields:

- `columns` (required for newly-created tables, array): ordered column width metadata. Each item's `width` is a positive, finite number in CSS pixels (`px`), without a unit suffix in JSON. The editor calculates initial widths from the available editor width and column count, with a minimum of `35px`.
- `ui` (required for newly-created tables, object): table display metadata such as `alternate_highlight`.
- `style.gridTemplateColumns` (required for newly-created tables, string): CSS grid column track list corresponding to the column metadata, for example `repeat(2, 336px)` or `300px 372px`. This CSS string includes length units.
- `style.gridAutoRows` (required for newly-created tables, string): CSS grid row sizing, initially `minmax(42px, auto)`.
- `table_row.style.min_height` (required for newly-created rows, number): positive, finite row minimum height in CSS pixels (`px`), without a unit suffix in JSON. New rows start at `42`.
- `table_cell.style` (required for newly-created cells, object): cell style.
- `table_cell.inherit_style` (required for newly-created cells, object): style inherited by inserted cells.

### Field Values

- `ui.alternate_highlight` (boolean): `true` enables alternating row highlighting; `false` disables it. The normal table insertion command uses `false` unless a table template requests highlighting.
- `table_cell.style.text_align` (string): horizontal alignment. The editor's menu supports `left`, `center`, and `right`.
- `table_cell.style.align_items` (string): vertical alignment. The editor's menu supports `flex-start` (top), `center`, and `flex-end` (bottom).
- `table_cell.style.background_color` (string): CSS background color. An absent field or an empty string applies no explicit cell background, allowing table highlighting or the surrounding background to remain visible.

Cell style fields can be absent when no explicit style has been set. `inherit_style` stores styles to apply when inserting cells; its `text_align` and `background_color` fields use the same value conventions as `style`. Numeric widths and heights are pixel values, while grid layout strings contain CSS length units. Editor minimum sizes describe creation and resizing behavior, rather than a blanket rejection rule for historical documents.

### Example

```json
{
  "id": "table-id",
  "type": "table",
  "columns": [
    { "width": 336 }
  ],
  "ui": {
    "alternate_highlight": false
  },
  "style": {
    "gridTemplateColumns": "repeat(1, 336px)",
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

### Compatibility

Historical documents may contain `style.alignItems`. New documents use `style.align_items`. Compatibility and migration behavior may depend on the reader implementation.
