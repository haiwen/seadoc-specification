# Divider

`divider` is a block-level void element representing a horizontal divider. It has no additional properties. It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Node Structure Example

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

## Compatibility

Historical documents may contain `type: "hr"`. New documents use `type: "divider"`. Compatibility and migration behavior may depend on the reader implementation.
