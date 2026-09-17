# Video

`video` is a block-level void element. It follows the [void element](../support-types.md#void-elements) placeholder rule.

## Required properties

- `data` (required, object): video data.
- `data.src` (required, string): video source.

## Optional properties
- `data.name` (optional, string or null): video filename or display name.
- `data.size` (optional, number or null): size in bytes.
- `data.is_embeddable_link` (optional, boolean): whether `src` is an embeddable video link. The default is `false`.
- `data.width` (optional, number): saved display width.

```json
{
  "id": "video-id",
  "type": "video",
  "data": {
    "src": "/video.mp4",
    "name": "video.mp4",
    "size": 2357967,
    "is_embeddable_link": false,
    "width": 640
  },
  "children": [
    {
      "id": "video-placeholder-id",
      "text": ""
    }
  ]
}
```
