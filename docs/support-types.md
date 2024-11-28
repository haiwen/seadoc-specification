# SeaDoc support node types

## Generic nodes
All nodes include the following attributes:  
`id` (required, string) represents a unique ID, a random UUID string with 22 characters for the node.  
`type` (required, string) represents the node type.  
`children` (required, array) represents an array of child nodes. The innermost within children are always text nodes.

## Node types
1. blockquote
2. callout
3. check_list_item
4. code_block
5. file_link
6. header
7. image
8. link
9. list
10. mention
11. multi_column
12. paragraph
13. sdoc_link
14. table
15. video
