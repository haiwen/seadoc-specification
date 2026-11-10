# Formula

`formula` is a block-level void element. Its formula source is stored in `data.formula`. It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Required Properties

- `data` (required, object): formula data.
- `data.formula` (required, string): formula source.

## Node Structure Example

```json
{
  "id": "formula-id",
  "type": "formula",
  "data": {
    "formula": "E = mc^2"
  },
  "children": [
    {
      "id": "formula-placeholder-id",
      "text": ""
    }
  ]
}
```
