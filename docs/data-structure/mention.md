# Mention

Mention type nodes represent a mention of participants or users with Sdoc. Along with generic node attributes, mention nodes includes the following attribute:

- `username` (required, string) is a unique string that identifies the participant.

Mention nodes contain a `text` node that always starts with `@` symbol followed by the  participant's name.

## Node structure example
```javascript  
{
  "id": "afLKcmNdR4ii2ZqvH8PP8w",
  "type": "mention",
  "username": "36029b7bffc74aae8a09fc5d453b99e2@auth.local",
  "children": [
    {
    "id": "bKfw6ms4QlqUf1J5aFCr4w",
    "text": "@username"
    }
  ]
}
```