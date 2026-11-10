# List

`ordered_list` and `unordered_list` are block element nodes that represent numbered lists and bulleted lists. Each list item is represented by a `list_item` structural element.

## Children

- Their `children` normally contain `list_item` elements. Text and inline elements belong inside each item's child blocks, rather than directly inside the list.
- A new `list_item` starts with a [paragraph](paragraph.md). It can also contain nested `ordered_list` or `unordered_list` blocks and [code blocks](code_block.md).

The normal structure is:

```text
ordered_list / unordered_list -> list_item -> paragraph -> text or inline elements
```

## Data Structure

### Ordered List { #ordered_list-nodes }

```json
{
  "id": "S927zAqWQHOkmLEvFespbw",
  "type": "ordered_list",
  "children": [
    {
      "id": "AW53tbxhQYu-HfoSNTfVxQ",
      "type": "list_item",
      "children": [{
        "id": "FZq5VuH8SM-_lE_UKI2GUw",
        "type": "paragraph",
        "children": [
          {
            "id": "NS1OQ71aQ0-VfxtMyqtszw",
            "text": "ordered list 1"
          }
        ]
      }]
    }, 
    {
      "id": "c-GkcbFsS3uuYNtMgsg2mQ",
      "type": "list_item",
      "children": [{
        "id": "PUoT91gOSoS8hB-HObsD1g",
        "type": "paragraph",
        "children": [
          {
            "id": "QEA-1fOPSSa0o3HPEGPPIg",
            "text": "ordered list 2"
          }
        ]
      }]
    }
  ]
}
```

### Unordered List { #unordered_list-nodes }

```json
{
  "id": "S927zAqWQHOkmLEvFespbw",
  "type": "unordered_list",
  "children": [
    {
      "id": "AW53tbxhQYu-HfoSNTfVxQ",
      "type": "list_item",
      "children": [{
        "id": "FZq5VuH8SM-_lE_UKI2GUw",
        "type": "paragraph",
        "children": [
          {
            "id": "NS1OQ71aQ0-VfxtMyqtszw",
            "text": "Unordered list 1"
          }
        ]
      }]
    }, 
    {
      "id": "c-GkcbFsS3uuYNtMgsg2mQ",
      "type": "list_item",
      "children": [{
        "id": "PUoT91gOSoS8hB-HObsD1g",
        "type": "paragraph",
        "children": [
          {
            "id": "QEA-1fOPSSa0o3HPEGPPIg",
            "text": "Unordered list 2"
          }
        ]
      }]
    }
  ]
}
```
