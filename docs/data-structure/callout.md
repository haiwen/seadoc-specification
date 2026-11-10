# Callout

`callout` is a block element node that represents emphasized content with a background color and an optional icon.

## Usage and Children

- Its `children` contain block elements such as [paragraphs](paragraph.md), [headings](header.md), [checklist items](check_list_item.md), [lists](list.md), and [blockquotes](blockquote.md). Inline content belongs inside those child blocks.
- A new callout commonly starts with a paragraph. The editor rejects pasted code blocks and tables; a pasted callout's wrapper is removed when inserting it into another callout.

## Data Structure

### Properties

- `style` (required, object): callout style.
- `style.background_color` (required, string): CSS background color. The editor-created default is `#fef7e0`. The editor's palette provides `#f1f3f6`, `#e1e9fe`, `#def0ff`, `#e7f9ee`, `#eaf7d6`, `#fef7e0`, `#fff1e8`, `#ffe6e3`, `#ffe9f2`, and `#fde8ff`. Other CSS colors can be rendered, but the editor's selected-border color mapping is defined for these palette entries.
- `callout_icon` (optional, string): one of `trumpet` (📢), `bulb` (💡), `prohibited` (🚫), or `warning` (⚠️). An absent field or an empty string means no icon is shown. Store the icon key, rather than the emoji character.

### Example

```json
{
  "id": "callout-id",
  "type": "callout",
  "style": {
    "background_color": "#fef7e0"
  },
  "children": [
    {
      "id": "callout-paragraph-id",
      "type": "paragraph",
      "children": [
        {
          "id": "callout-text-id",
          "text": "Callout content"
        }
      ]
    }
  ]
}
```
