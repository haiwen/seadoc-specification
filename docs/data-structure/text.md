# Text

A text node is a leaf node that stores text content and optional formatting marks.

## Children

- Plain text does not require an inline wrapper.
- Void elements also retain text children as structural placeholders or stored display labels; those children are not ordinary editable text.
- A text node has no children.

## Data Structure

### Properties

A text leaf has:

- `id` (required, string): unique node identifier.
- `text` (required, string): displayed text.

Text leaves do not require `type` or `children`.

### Example

```json
{
  "id": "text-id",
  "text": "Text content"
}
```

### Text Formatting (Marks)

Text leaves may carry the following formatting fields:

- `bold`, `italic`, `underline`, `strikethrough`, `superscript`, `subscript`, and `code` (optional, boolean): `true` enables the corresponding mark; `false` or an absent field leaves it disabled.
- `color` (optional, string): CSS text color, such as `#ff0000` or `rgb(255, 0, 0)`. An absent field or an empty string applies no explicit text color, so the surrounding style determines the color.
- `highlight_color` (optional, string): CSS background color, such as `#fff1e8` or `rgba(255, 241, 232, 0.5)`. An absent field or an empty string applies no explicit highlight.
- `font_size` (optional, number): positive, finite font size in points (`pt`), without a unit suffix in JSON. Fractional values are supported. For example, `12` means `12pt`, not `12px`. An absent field inherits the surrounding font size; the editor's ordinary body-text default is `11pt`, while headings and other specialized blocks can use different defaults.
- `font` (optional, string): font family name, such as `Arial` or `Noto Sans SC`, or `default_font` for the editor's default font stack. An absent field or an empty string inherits the surrounding font. Font availability and fallback depend on the reader environment.

Serialize font sizes as numbers, rather than strings such as `"12pt"`. Colors may use CSS color representations beyond hexadecimal.

Revision, diff, comment, selection, cursor, AI, and syntax-decoration fields are not ordinary rich-text formatting fields in this specification.
