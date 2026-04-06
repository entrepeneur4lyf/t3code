---
name: feature-or-settings-development-with-tests-and-docs
description: Workflow command scaffold for feature-or-settings-development-with-tests-and-docs in t3code.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-settings-development-with-tests-and-docs

Use this workflow when working on **feature-or-settings-development-with-tests-and-docs** in `t3code`.

## Goal

Implements a new feature or settings option, updating implementation, tests, and related documentation/UI files.

## Common Files

- `apps/web/src/appSettings.ts`
- `apps/web/src/appSettings.test.ts`
- `apps/web/src/components/ChatView.tsx`
- `apps/web/src/routes/_chat.settings.tsx`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Implement feature logic in main code file(s)
- Update or add corresponding test files
- Update UI components as needed
- Update documentation or settings files if applicable

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.