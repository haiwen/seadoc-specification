# Toggle header

`toggle_header` is a block container with a title and collapsible content. Its title child is one of `toggle_header1`, `toggle_header2`, or `toggle_header3`. Each title contains text leaves. Expanded content is held by a `toggle_content` child containing block elements.

## Expanded structure

An expanded toggle has `collapsed: false` and two children: title first, then `toggle_content`.

```json
{
  "id": "toggle-id",
  "type": "toggle_header",
  "collapsed": false,
  "children": [
    {
      "id": "toggle-title-id",
      "type": "toggle_header1",
      "children": [
        {
          "id": "toggle-title-text-id",
          "text": "Title"
        }
      ]
    },
    {
      "id": "toggle-content-id",
      "type": "toggle_content",
      "children": [
        {
          "id": "toggle-paragraph-id",
          "type": "paragraph",
          "children": [
            {
              "id": "toggle-body-text-id",
              "text": "Body"
            }
          ]
        }
      ]
    }
  ]
}
```

## Collapsed structure

When collapsed, `collapsed` is `true`. The content formerly held by `toggle_content.children` is stored in `collapsed_body`, and `children` retains only the title.

```json
{
  "id": "toggle-id",
  "type": "toggle_header",
  "collapsed": true,
  "collapsed_body": [
    {
      "id": "toggle-paragraph-id",
      "type": "paragraph",
      "children": [
        {
          "id": "toggle-body-text-id",
          "text": "Body"
        }
      ]
    }
  ],
  "children": [
    {
      "id": "toggle-title-id",
      "type": "toggle_header1",
      "children": [
        {
          "id": "toggle-title-text-id",
          "text": "Title"
        }
      ]
    }
  ]
}
```

## Compatibility

`collapsed_body` is part of the collapsed representation and preserves the hidden content.
