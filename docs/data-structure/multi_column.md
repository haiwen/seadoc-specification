# Multi column

Multi-column type nodes represent a layout with multiple columns, useful for displaying content in a structured and side-by-side format. Along with generic node attributes, multi-column nodes include the following attributes:

- `gridTemplateColumns` (required, string) specifies the column layout using CSS grid syntax, defining the number of columns and their respective widths.

- `columns` (required, array) defines an array of width and left position of each column.

Multi-column nodes includes multiple `column` (required, node) nodes, each representing an individual column in the layout. Each column node contains a `paragraph` node, which in turn holds a `text` node that displays the column content.

## Node structure example
```javascript  
{

  "id": "ZO5pAIMaTLyuKMUswc02NA",
  "type": "multi_column", 
  "style": "repeat(3, 224px)",
  "columns": [
    {
      "key": "dypqfMOuTZCKwCa13QQ5-A", 
      "width": 200, 
      "left": 200
    },
    {
      "key": "dEUv4oFgS52Awuxt-_h7ZA", 
      "width": 248, 
      "left": 248
    }
    {
      "key": "VLqGwLUyQQuEZ6X-nBnq9g", 
      "width": 224, 
      "left": 224
    }
  ]
  "children": [ 
    {
      "id": "dypqfMOuTZCKwCa13QQ5-A", 
      "type": "column",
      "width": 200,
      "children": [ 
        {
          "id": 'Vtvx0SEOSZuyrsNug2hhLQ', 
          "type": 'paragraph',
          "children": [
            {
              "text": "column 1 content", 
              "id": "D25vYec_T2S68pZx3JKiaw" 
            }
          ]
        }
      ]
    },
    {
      "id" "dEUv4oFgS52Awuxt-_h7ZA",
      "type": "column",
      "width": 248,
      "children": [ 
        {
          "id": 'T34vx0SEOSZuyrsNug2hhLQ', 
          "type": 'paragraph',
          "children": [
            {
              "text": "column 2 content", 
              "id": "R455vYec_T2S68pZx3JKiaw" 
            }
          ]
        }
      ]
    },
    {
      "id": "VLqGwLUyQQuEZ6X-nBnq9g",
      "type": "column",
      "width": 224,
      "children": [ 
        {
          "id": "FIJxlp7XRbOOVd-Mc-pzoQ", 
          "type": 'paragraph',
          "children": [
            {
              "text": "column 3 content", 
              "id": "OEtHz_AlQSO99dj9SiTPug" 
            }
          ]
        }
      ]
    },     
  ],
}
```