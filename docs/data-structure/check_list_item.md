# Check_list_item

`check_list_item` is a block element representing a checklist item.

## Properties

- `checked` (required, boolean): completion state. The editor-created default is `false`.

Its `children` contain text leaves and supported inline elements.

```json
{
  "id": "check-list-id",
  "type": "check_list_item",
  "checked": false,
  "children": [
    {
      "id": "check-list-text-id",
      "text": "Checklist content"
    }
  ]
}
```
