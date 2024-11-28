# Code_block

Code_block type nodes represent a block of code. Along with generic node attributes, code_block nodes include the following attribute:

- `language` (required, string) specifies the programming language used in the code. The default value is 'plaintext'.

- `white_space` (requires, string) specifies how white space should be handled in the block. The default value is 'nowrap'.

Code_block nodes contains `code-line` child nodes, where each code-line node represents a single line of the code. Each code-line node holds a `text` node that displays the code content.

## Node structure example
```javascript  
{
  "id": "Sgs2yIs4RHO4YVRb0rGunQ",
  "type": "code_block",
  "language": "javascript",
  "style": {
      "white_space": "nowrap"
  },
  "children": [
    {
      "id": "N4QoQh3-RFSQzvaTgJityQ",
      "type": "code_line",
      "children": [
        {
          "text": "code content1",
          "id": "P95HPWnYTay4FkT1BQ27tw"
        }
      ]
    }, 
    {
      "id": "DKbt3HrRSY6A5zYEI3UEpg",
      "type": "code_line",
      "children": [
        {
          "text": "code content2';",
          "id": "O3Hcb450Q5Cd1inMrjksYw"
        }
      ]
    }
    ...
  ]
}
```