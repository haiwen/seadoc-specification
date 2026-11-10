# Heading { #header }

`header1` through `header6` are block element nodes that represent six levels of headings. `title` and `subtitle` represent document titles and subtitles and use the same node structure.

## Usage and Children

- Their `children` directly contain [text nodes](text.md) and supported inline elements, such as [links](link.md). Content following a heading remains in sibling blocks, rather than becoming its children.
- The editor moves images out of `header1` through `header6` into a following paragraph.
- Set `type` to `title` or `subtitle` to use the same structure for a title or subtitle.

## Data Structure

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
