# Video

Video type nodes represents video content. Along with generic node attributes, video nodes include `data`(required, object) attribute with the following properties:

- `src` (required, string) specifies the video address within Sdoc.

- `videoFiles` (required, object) provides metadata about the video file, containing the following attributes: 

    - `filename` (required, string) is the name of the video file.
    
    - `lastModified`(required, number) indicates the timestamp of the last modification in milliseconds since the Unix epoch.
    
    - `lastModifiedDate`(required, Date) specifies the date and time when the video file was last modified.
    
    - `size`(required, number) is the size of the video file in bytes.


Video nodes contain an empty `text` node.

## Node structure example
```javascript
{
  "id": "c5o2vli_St6hAQyHdvwGkg",
  "type": "video",
  "data": {
    "src": "/video-Hd3JcWkARqyJ-I0geiIgPQ.mov",
    "videoFiles": {
      "name": "video name.mov",
      "lastModified": 1731406823157,
      "lastModifiedDate": Tue Nov 12 2024 18:20:23 GMT+0800,
      "size": 2357967
    }
  }
  "children": [
    {
      "id": "YcA-XKAAQf6Ff7V7Xj4KaA",
      "text": "",
    }
  ]
}
```