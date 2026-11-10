# Formula

`formula` is a block element node that represents a mathematical formula. It is a void element whose formula source is stored in `data.formula`.

## Usage and Children

- Its `children` contain one empty [text node](text.md) as a structural placeholder. The formula source is stored in `data.formula`, rather than in editable child text. See [Void Elements](../support-types.md#void-elements).

## Data Structure

### Required Properties

- `data` (required, object): formula data.
- `data.formula` (required, string): TeX/LaTeX math source passed to the editor's MathJax renderer, such as `E = mc^2` or `\frac{a}{b}`. Store the math source without surrounding `$`, `$$`, `\(`, or `\[` delimiters. Backslashes must be escaped in JSON, for example `"\\frac{a}{b}"`. An empty string has no visible formula content; supported commands depend on the reader's MathJax configuration.

### Example

```json
{
  "id": "formula-id",
  "type": "formula",
  "data": {
    "formula": "E = mc^2"
  },
  "children": [
    {
      "id": "formula-placeholder-id",
      "text": ""
    }
  ]
}
```
