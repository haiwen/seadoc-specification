# Multi column

`multi_column` is a block layout element. Its direct children are `column` structural elements.

## Editor-created defaults

- `column` (required for newly-created layouts, array): column metadata. Each item contains `key`, `width`, and may contain `left`.
- `style.gridTemplateColumns` (required for newly-created layouts, string): CSS grid column layout.

Each child `column` has:

- `id` (required, string): normally corresponding to the metadata `key`.
- `type` (required): `column`.
- `width` (required for newly-created columns, number).
- `children` (required, array): block content. A new column begins with a paragraph and text leaf.

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
