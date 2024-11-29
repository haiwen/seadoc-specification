# List

List-related type nodes are used to represent ordered and unordered lists. List-related nodes consist of the following node types:

**Ordered_list nodes**

`ordered_list`  nodes represent an ordered list, where items are numbered.

**Unordered_list nodes**

`unordered_list` nodes represent an unordered list, where items are marked with bullet points.

Both of list nodes include `list_item`（required, node）child nodes, representing individual items within the list.
Each list_item node contains a `paragraph` node, which in turn holds a `text` node that displays the content of the list item.

## Node structure example

### Ordered_list nodes
```javascript  
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
    },
    ...
  ]
}
```
### Unordered_list nodes
```javascript  
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
    },
    ...
  ]
}
```