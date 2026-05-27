---
name: feature-or-bugfix-with-test
description: Workflow command scaffold for feature-or-bugfix-with-test in numo-narray.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-bugfix-with-test

Use this workflow when working on **feature-or-bugfix-with-test** in `numo-narray`.

## Goal

Implement a feature or bugfix in the C extension and add/modify corresponding Ruby tests.

## Common Files

- `ext/numo/narray/numo/types/*.h`
- `test/*.rb`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add implementation in ext/numo/narray/numo/types/*.h or related C files.
- Update or add tests in test/*.rb.
- Commit and push changes.
- Merge pull request if applicable.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.