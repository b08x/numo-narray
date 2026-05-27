---
name: ci-workflow-update
description: Workflow command scaffold for ci-workflow-update in numo-narray.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /ci-workflow-update

Use this workflow when working on **ci-workflow-update** in `numo-narray`.

## Goal

Update, fix, or enhance the GitHub Actions CI workflow (e.g., add Ruby versions, Fedora builds, fix deprecations).

## Common Files

- `.github/workflows/build.yml`
- `numo-narray.gemspec`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit .github/workflows/build.yml to add or update jobs, runners, or steps.
- Optionally update related files (e.g., numo-narray.gemspec) if dependency or Ruby version changes are involved.
- Commit and push changes.
- Merge pull request if applicable.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.