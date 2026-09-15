# Link

`link` is an inline element. It normally appears in the children of a text block such as a [paragraph](paragraph.md).

## Required properties

- `href` (required, string): URL target. It may be an empty string when `linked_id` or `linked_wiki_page_id` supplies the target.
- `title` (required, string): display title.

## Optional properties
- `linked_id` (optional, string): target element ID for an in-document link. Editor-created links use an empty string when no element target is set.
- `linked_wiki_page_id` (optional, string): target wiki page ID. Editor-created wiki links use an empty string when no page target is set.

## Structure

`children` contains the text leaf or leaves that display the link.

At least one of `href`, `linked_id`, or `linked_wiki_page_id` must be a non-empty string. `title` and text children are display content, not target identifiers.

| Link kind | Non-empty target field | Example |
| --- | --- | --- |
| URL link | `href` | `{ "href": "https://example.com", "linked_id": "", "linked_wiki_page_id": "" }` |
| In-document link | `linked_id` | `{ "href": "", "linked_id": "target-element-id", "linked_wiki_page_id": "" }` |
| Wiki page link | `linked_wiki_page_id` | `{ "href": "", "linked_id": "", "linked_wiki_page_id": "target-page-id" }` |

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
