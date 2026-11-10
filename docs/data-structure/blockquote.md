# Blockquote

`blockquote` is a block element node that represents quoted content, citations, or references.

## Usage and Children

- Its `children` contain block elements, commonly [paragraphs](paragraph.md), [headings](header.md), [lists](list.md), and [checklist items](check_list_item.md). A blockquote can contain more than one block.
- Text and inline elements belong inside those child blocks, rather than directly inside the blockquote.
- When code blocks or tables are pasted into a blockquote, the editor places those elements outside the quote.

## Data Structure

```json
{
  "id": "awGPshsHSry9cQJuKxvHGg",
  "type": "blockquote",
  "children": [
    {
      "id": "VVKieoeQRa-b8UP-AxnVIg",
      "type": "paragraph",
      "children": [
        {
          "id": "JT6oOyplQm-270FdGw_M-A",
          "text": "Quote content"
        }
      ]
    }
  ]
}
```
