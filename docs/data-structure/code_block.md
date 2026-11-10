# Code Block { #code_block }

`code_block` is a block element node that represents source code across one or more lines.

## Usage and Children

- Its `children` are `code_line` block elements. Each code line contains [text nodes](text.md) representing one line of code, rather than paragraph or inline link elements.
- Pasted content is converted into code-line text.

```text
code_block -> code_line -> text leaf
```

## Data Structure

### Required Properties

- `language` (required, string): language identifier, such as `javascript`, rather than the display label `Javascript`. Common values include `plaintext`, `bash`, `css`, `c`, `cpp`, `csharp`, `go`, `html`, `javascript`, `java`, `json`, `php`, `python`, `ruby`, `sql`, `swift`, `typescript`, `xml`, and `yaml`.

### Optional Properties

- `style` (optional, object): code display settings.
- `style.white_space` (optional, string): `nowrap` disables visual line wrapping; `normal` enables it. Visual wrapping does not create additional `code_line` nodes. When the style object is absent, the editor uses `nowrap`.

### Editor-Created Defaults

- `language` may be an empty string or `plaintext` when no programming language is set. The historical value `text` also represents plain text.
- `style.white_space` is `nowrap` for a newly-created block.

`language` is the native `.sdoc` field.

### Example

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
