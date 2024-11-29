# Blockquote

Blockquote type nodes represent quoted content, typically used to highlight or display citations, quotes, or references. 
Blockquote nodes contain a `paragraph` node, which in turn holds a `text` node that displays the quoted content.

## Node structure example
```javascript  
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