# Publication Date

This is a development note. Runtime publication-date rules live in `skills/_shared/reference/publication-date.md`.

When changing issue-date inference or date-range logic:

- Update `skills/_shared/reference/publication-date.md`.
- Update `newsletter-articles`, `newsletter-events`, and `newsletter-anniversary` if their workflow-specific windows change.
- Update examples or tests that assume a nearest-Monday publication date.
- Use concrete dates in user-facing explanations when there is any ambiguity.
