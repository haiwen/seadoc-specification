# Callout

`callout` is a block container used to emphasize content.

## Properties

- `style` (required, object): callout style.
- `style.background_color` (required, string): background color. The editor-created default is `#fef7e0`.

Callout content is stored in `children`. A paragraph is the common initial content structure, but this page does not impose a narrower child grammar than the persisted format requires.

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
