# Header

Header type nodes represent the header content, supporting six header type nodes (`header1`  to `header6`). `title` and `subtitle` use the same node shape, with `type` set to `title` or `subtitle`. They do not have separate structure pages.

Header nodes contain text leaves that display the header content.

## Node structure example
```json
{
  "id": "G1opTnrHRr6aX7qbJXZJiw",
  "type": "header1",
  "children": [
    {
      "id": "D_bLOntqQHSZ8lu9VJn_JQ",
      "text": "header content"
    }
  ]
}
```
