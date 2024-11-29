# Sdoc_link

Sdoc_link type nodes reference a link to another Sodc file. Sdoc_link nodes are inline nodes, typically wrapped within `paragraph` nodes. Along with generic node attributes, sdoc_link nodes include the following attributes:

- `doc-uuid` (required, string) represents the file address within Sdoc.

- `title` (required, string) represents the filename.

- `display-type` (required, string) represents display type of file.

Sdoc_link nodes contain a `text` node that displays the filename.

## Node structure example
```javascript  
{
  "id": "afLKcmNdR4ii2ZqvH8PP8w",
  "type": "sdoc_link",
  "doc_uuid": "c24cee20-88c2-4dba-beb9-4032c5e2c3e1",
  "title": "aaa.sdoc",
  "display_type": "text_link",
  "children": [
    {
    "id": "bKfw6ms4QlqUf1J5aFCr4w",
    "text": "aaa.sdoc"
    }
  ]
}
```