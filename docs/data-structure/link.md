# Link

Link type nodes reference a hyperlink within the text content. Link nodes are inline nodes, typically wrapped within `paragraph` nodes. Along with generic node attributes, link nodes include the following attributes:

- `href` (required, string) represents the URL of the link. 

- `title` (required, string) represents the display text of the link.

Link nodes contain a `text` node that displays the actual text content of the link.

## Node structure example
```javascript  
{
  "id": "eduiixSdSwudGpUcqWrPqA",
  "type": "link",
  "href": "http://127.0.0.1:4000/simple-markdown-editor",
  "title": "text content",
  "children": [
    {
    "id": "acHUS5G5SP-0ltl04_rdzg",
    "text": "text content"
    }
  ]
}
```