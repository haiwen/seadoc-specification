# Callout
Callout type nodes are used to highlight specific content, often for emphasis. Along with generic node attributes, callout nodes include the following attribute:

- `background_color` (required, string)  represents the highlighted background color. The default value is '#fef7e0'.

Callout nodes contain a `paragraph` node, which in turn holds a `text` node that display the callout content.

## Node structure example
```javascript  
{
  "id": "U2DUIYK1T6qEAtCORbB1ZA", 
  "type": "callout",
  "style": { "background_color": "#fef7e0" }
  "children": [
    {
      "id": "cCs57hn6SfmVHclXYzZ6RQ",
      "type": "paragraph",
      "children": [
        {
        "id": "JT6oOyplQm-270FdGw_M-A",
        "text": "Callout content"
        }
      ]
    }
  ]
}
```