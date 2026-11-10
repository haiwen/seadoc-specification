# Link

`link` is an inline element node that represents a hyperlink to a URL, a document element, or a wiki page. It is a non-void element with editable link text.

## Usage and Children

- It appears inside a text block such as a [paragraph](paragraph.md), [heading](header.md), [checklist item](check_list_item.md), or [table cell](table.md), rather than directly in the document's `elements` list.
- Its `children` contain one or more [text nodes](text.md) forming the link label. Separate leaves can carry different formatting marks.
- Its label is editable child content; it does not contain block elements.

## Data Structure

### Required Properties

- `href` (required, string): absolute HTTP(S) URL target. It may be an empty string when `linked_id` or `linked_wiki_page_id` supplies the target.
- `title` (required, string): display title.

### Optional Properties

- `linked_id` (optional, string): target element ID for an in-document link. Editor-created links use an empty string when no element target is set.
- `linked_wiki_page_id` (optional, string): target wiki page ID. Editor-created wiki links use an empty string when no page target is set.

### Link Targets

At least one of `href`, `linked_id`, or `linked_wiki_page_id` must be a non-empty string. `title` and text children are display content, not target identifiers.

| Link kind | Non-empty target field | Example |
| --- | --- | --- |
| URL link | `href` | `{ "href": "https://example.com", "linked_id": "", "linked_wiki_page_id": "" }` |
| In-document link | `linked_id` | `{ "href": "", "linked_id": "target-element-id", "linked_wiki_page_id": "" }` |
| Wiki page link | `linked_wiki_page_id` | `{ "href": "", "linked_id": "", "linked_wiki_page_id": "target-page-id" }` |

### Example

```json
{
  "id": "link-id",
  "type": "link",
  "href": "https://example.com/docs",
  "title": "SeaDoc documentation",
  "linked_id": "",
  "linked_wiki_page_id": "",
  "children": [
    {
      "id": "link-text-id",
      "text": "SeaDoc documentation"
    }
  ]
}
```
