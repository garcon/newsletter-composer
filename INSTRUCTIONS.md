# Newsletter Composer - Development Instructions

This repository contains a GitHub Copilot plugin for composing and managing newsletters from notes prepared in an Obsidian vault.

Maintain this directory as development documentation for the plugin itself. Runtime workflow rules that an agent needs while composing newsletters should live in the relevant skill, or in shared skill references under `skills/_shared/reference/`.

## Instruction Files

- [Primary Use](instructions/primary-use.md) - development-level product purpose and supported environment.
- [Newsletters](instructions/newsletters.md) - maintenance note for newsletter identities; runtime facts live in `skills/_shared/reference/newsletter-context.md`.
- [Obsidian Vault Structure](instructions/obsidian-vault-structure.md) - maintenance note for vault assumptions; runtime structure lives in `skills/_shared/reference/vault-structure.md`.
- [Section Map](instructions/section-map.md) - maintenance note for section mapping; runtime map lives in `skills/_shared/reference/section-map.md`.
- [Approval Workflow](instructions/approval-workflow.md) - maintenance note for approval behavior; runtime approval rules live in `skills/_shared/reference/approval-workflow.md`.
- [Publication Date](instructions/publication-date.md) - maintenance note for date inference; runtime date rules live in `skills/_shared/reference/publication-date.md`.
- [Platform Adapters](instructions/platform-adapters.md) - documents the GitHub Copilot CLI and Claude Code compatibility layers.
- [Plugin Resources](instructions/plugin-resources.md) - development note for shared examples and reference material.
- [Ongoing Rules](instructions/ongoing-rules.md) - durable maintenance rules for evolving the plugin.

## Runtime Rule Placement

- Put section-specific workflow rules in that section's `SKILL.md`.
- Put shared runtime rules used by multiple skills in `skills/_shared/reference/`.
- Put examples that a skill actively uses in that skill's `reference/` folder.
- Keep `instructions/` focused on plugin development, maintenance, and source-of-truth pointers.
- Keep `newsletter-vault-structure` in `skills/99-vault-structure/` aligned with shared vault rules whenever vault structure expectations change.
