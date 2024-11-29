# Table

Table type nodes represent a table. Along with generic node attributes, table nodes include the following attributes:
- `gridTemplateColumns` (required, string) specifies the column layout using CSS grid syntax, defining the number of columns and their respective widths.

- `gridAutoRows` (required, string) specifies the minimum height for each row.

- `columns` (required, array) defines an array of width of each column metadata.

Table nodes includes `table_row`(required, node) child nodes, representing rows within table. Each table_row node contains `table_cell`(required, node) child nodes, representing individual cells within a row. Each table_cell node contains a `text` node that displays the content of th cell.

## Node structure example
```javascript  
{
  "id": "G70G_NH_QF-WvJLlFPG1bg",
  "type": "table",
  "style": {
    "gridAutoRows": "minmax(42px, auto)", 
    "gridTemplateColumns": "repeat(2, 336px)"
  }
  "columns": [
    { "width": 336 },
    { "width": 336 }
  ]
  "children": [
    {
      "id": "Mr8wLrYBQOeKlvni1HywUw",
      "type": "table_row",
      "style": { "min_height": 42 }
      "children": [
        {
          "id": "BiWIgCy0TqecA3DsXqOh7Q",
          "type": "table_cell",
          "children": [{
              "text": "name",
              "id": "KlwwLiWAQVi7uLQlRuJjdg"
          }]
        }, 
        {
          "id": "Tpx8x7afTzWhjCcBxmus2g",
          "type": "table_cell",
          "children": [{
              "text": "class",
              "id": "M13HGrtGSV6e0g-dB8cw3A"
          }]
        }
      ],
    }, 
    {
      "id": "Mr8wLrYBQOeKlvni1HywUw",
      "type": "table_row",
      "style": { "min_height": 42 }
      "children": [
        {
          "id": "BiWIgCy0TqecA3DsXqOh7Q",
          "type": "table_cell",
          "children": [{
              "text": "name",
              "id": "KlwwLiWAQVi7uLQlRuJjdg"
          }]
        }, 
        {
          "id": "Tpx8x7afTzWhjCcBxmus2g",
          "type": "table_cell",
          "children": [{
              "text": "class",
              "id": "M13HGrtGSV6e0g-dB8cw3A"
          }]
        }
      ],
    }, 
    ...
  ]
}
```