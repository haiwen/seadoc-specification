# Paragraph

`paragraph` is a block element node that represents a paragraph of rich text.

## Children

- Its `children` directly contain [text nodes](text.md) and supported inline elements, such as [links](link.md), [images](image.md), [file links](file_link.md), and [SeaDoc links](sdoc_link.md).
- Plain text does not require an inline wrapper. A paragraph does not contain other block elements.

## Data Structure

```json
{
  "id": "afLKcmNdR4ii2ZqvH8PP8w",
  "type": "paragraph",
  "children": [
    {
      "id": "bKfw6ms4QlqUf1J5aFCr4w",
      "text": "text content"
    }
  ]
}
```
