# Whiteboard

`whiteboard` is a block element node that references a whiteboard file. It is a void element.

## Usage and Children

- Its `children` contain one empty [text node](text.md) as a structural placeholder. The file reference and display information belong in the element's properties, rather than editable child text. See [Void Elements](../support-types.md#void-elements).

## Data Structure

### Required Properties

- `repo_id` (required, string): repository identifier containing the whiteboard file.
- `title` (required, string): whiteboard filename or display title.
- `file_path` (required, string): path to the whiteboard file.
- `link` (required, string): read-only whiteboard link.

### Example

```json
{
  "id": "whiteboard-id",
  "type": "whiteboard",
  "repo_id": "repo-id",
  "title": "Architecture.exdraw",
  "file_path": "/Design/Architecture.exdraw",
  "link": "https://example.com/whiteboard/read-only-link",
  "children": [
    {
      "id": "whiteboard-placeholder-id",
      "text": ""
    }
  ]
}
```
