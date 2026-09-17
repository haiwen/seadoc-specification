# Whiteboard

`whiteboard` is a block-level void element that references a whiteboard file. It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Required properties

- `repo_id` (required, string): repository identifier containing the whiteboard file.
- `title` (required, string): whiteboard filename or display title.
- `file_path` (required, string): path to the whiteboard file.
- `link` (required, string): read-only whiteboard link.

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
