# Divider

`divider` is a block element node that represents a horizontal divider. It is a void element and has no additional properties.

## Children

- Its `children` contain one empty [text node](text.md) as a structural placeholder, rather than editable content. See [Void Elements](../support-types.md#void-elements).

## Data Structure

```json
{
  "id": "divider-id",
  "type": "divider",
  "children": [
    {
      "id": "divider-placeholder-id",
      "text": ""
    }
  ]
}
```

### Compatibility

Historical documents may contain `type: "hr"`. New documents use `type: "divider"`. Compatibility and migration behavior may depend on the reader implementation.
