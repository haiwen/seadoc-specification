# Title

`title` is a block element node that represents a document title.

## Children

- Its `children` directly contain [text nodes](text.md) and supported inline elements, such as [links](link.md). Content following a title remains in sibling blocks, rather than becoming its children.

## Data Structure

```json
{
  "id": "G1opTnrHRr6aX7qbJXZJiw",
  "type": "title",
  "children": [
    {
      "id": "D_bLOntqQHSZ8lu9VJn_JQ",
      "text": "title content"
    }
  ]
}
```
