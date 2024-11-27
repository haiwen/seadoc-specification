# Image

Image-related type nodes represent images within Sdoc. Image-related nodes consist of the following node types:

**Image nodes**

`image` nodes are inline nodes, typically wrapped within `paragraph` nodes. Along with generic node attributes, image nodes include the following attribute:

  - `data` (required, object) contains `src` (required, string) field that specifies the image address within Sdoc.

**Image_block nodes**

`Image_block` nodes represents block-level element containing a single inline image node that spans the entire width of the block.



## Node structure example

### Image nodes
```javascript  
{
  "id": "c-GkcbFsS3uuYNtMgsg2mQ",
  "type": "image",
  "data": {
    "src": "/image-aYZp6SvrTQyBbMOkxo0s6Q.png"
  }
  "children": [
    {
      "id": "PUoT91gOSoS8hB-HObsD1g",
      "text": "",
    }
  ]
}
```

### Image_block nodes
```javascript  
{
  "id": "S927zAqWQHOkmLEvFespbw",
  "type": "image_block",
  "children": [
    {
      "id": "AW53tbxhQYu-HfoSNTfVxQ",
      "text": "",
    }, 
    {
      "id": "c-GkcbFsS3uuYNtMgsg2mQ",
      "type": "image",
      "data": {
        "src": "/image-aYZp6SvrTQyBbMOkxo0s6Q.png"
      }
      "children": [
        {
          "id": "PUoT91gOSoS8hB-HObsD1g",
          "text": "",
        }
      ]
    },
    {
      "id": "AW53tbxhQYu-HfoSNTfVxQ",
      "text": "",
    }, 
  ]
}
```