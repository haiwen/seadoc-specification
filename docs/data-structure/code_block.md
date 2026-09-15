# Code_block

`code_block` is a block element with the following structure:

```text
code_block -> code_line -> text leaf
```

`code_line` is a structural child type. Each code line contains text leaves representing one code line.

## Required properties

- `language` (required, string): programming language.

## Editor-created defaults

- `language` may be an empty string or `plaintext` when no programming language is set.
- `style.white_space` is `nowrap` for a newly-created block.

`language` is the native `.sdoc` field.

```json
{
  "id": "code-block-id",
  "type": "code_block",
  "language": "javascript",
  "style": {
    "white_space": "nowrap"
  },
  "children": [
    {
      "id": "code-line-one-id",
      "type": "code_line",
      "children": [
        {
          "id": "code-text-one-id",
          "text": "const value = 1;"
        }
      ]
    },
    {
      "id": "code-line-two-id",
      "type": "code_line",
      "children": [
        {
          "id": "code-text-two-id",
          "text": "console.log(value);"
        }
      ]
    }
  ]
}
```
