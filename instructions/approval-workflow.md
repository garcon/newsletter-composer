# Approval Workflow

Use this workflow for section outputs that require explicit human approval before they are inserted into the final issue.

## Front Matter

Working section folder notes that require approval must contain YAML front matter:

```yaml
---
approved: waiting
---
```

If a working section folder note already exists and has no `approved` property, add `approved: waiting`.

## Approved Values

Treat these values as approved:

- `approved: approved`
- `approved: true`
- `approved: "true"`

All other values mean the section is not approved, including missing `approved`, `waiting`, `false`, and empty values.

## Final Insertion

When inserting an approved working output into an issue folder note:

- Remove YAML front matter.
- Preserve editor wording, links, emphasis, images, and paragraph structure.
- Do not rewrite approved human-edited text unless the user explicitly asks for it.
- Do not insert unapproved sections.
- If a section is not approved, leave its template placeholder unchanged and report it to the human editor.

