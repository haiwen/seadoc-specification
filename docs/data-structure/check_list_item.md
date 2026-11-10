# Checklist Item { #check_list_item }

`check_list_item` is a block element node that represents a checklist item with a completion state.

## Usage and Children

- Its `children` directly contain [text nodes](text.md) and supported inline elements, such as [links](link.md).
- Each checklist item is its own block.

## Data Structure

### Properties

- `checked` (required, boolean): completion state. The editor-created default is `false`.

### Example

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
