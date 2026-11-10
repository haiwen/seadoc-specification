# Video

`video` is a block element node that represents an uploaded video or an embeddable video link. It is a void element.

## Usage and Children

- It normally appears as a standalone block in the document's `elements` list.
- Its `children` contain one empty [text node](text.md) as a structural placeholder. The video source and display settings belong in `data`, rather than editable child text. See [Void Elements](../support-types.md#void-elements).

## Data Structure

### Required Properties

- `data` (required, object): video data.
- `data.src` (required, string): non-empty video source. Uploaded videos use an asset path or an absolute HTTP(S) URL. When `data.is_embeddable_link` is `true`, this is the provider's embeddable-player URL, rather than its ordinary watch-page URL.

### Optional Properties

- `data.name` (optional, string or null): video filename or display name. When absent, `null`, or empty, the editor uses `data.src` as the display name.
- `data.size` (optional, number or null): non-negative integer size in bytes. An absent field or `null` means the size is unknown, rather than zero bytes.
- `data.is_embeddable_link` (optional, boolean): `true` renders `src` in an embedded player; `false` renders it as a video file. An absent field behaves as `false`.
- `data.width` (optional, number): positive, finite display width in CSS pixels (`px`), without a unit suffix in JSON. When omitted, the editor uses `100%` of the available container width.

The video resize control has a minimum width of `150px`. This interaction limit is not a lower bound on every previously saved positive width.

### Example

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
