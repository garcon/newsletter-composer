# Approval Workflow

This is a development note. Runtime approval rules live in `skills/_shared/reference/approval-workflow.md`.

When changing approval behavior:

- Update `skills/_shared/reference/approval-workflow.md`.
- Update every skill that creates or consumes approval-gated output.
- Update `newsletter-finalize-issue` whenever insertion behavior changes.
- Update `README.md` so editors know how to approve a section.
- Keep the default state conservative: generated work should not enter final output before human approval when approval is required.
