---
name: git-commit-message-generator
description: Generate git commit messages from staged changes. Use when the user asks to write, draft or suggest a commit message.
---

# git-commit-message-generator

1. Run `git diff --staged --stat` for an overview, then `git diff --staged` for details. If nothing is staged, tell the user and stop.
2. Classify the changes using the types in "Commit types". Tests and docs that support a code change in the same commit belong to that change's type, not to test or docs. Only treat changes as separate types when they are independent of each other, e.g. an unrelated bug fix alongside a new feature. If they span more than one type, list which files belong to each type, suggest splitting them into separate commits, and ask the user whether to split or commit together. If committing together, use the type of the most significant change: feat > fix > perf > refactor > test > docs > chore.
3. Write the message in Conventional Commits 1.0.0 format, in English:
   - Summary line: `<type>(<scope>): <summary>`, under 50 characters, imperative mood.
   - Scope: the name of the main module or directory changed. Omit the scope if the changes span the whole project.
   - Body: for non-trivial changes, add a blank line, then explain what changed and why, wrapped at 72 characters. Take the reason only from the diff (e.g. code comments, a linked issue) or from the conversation; never guess it. If the reason is not evident, put `[WHY: ...]` where it belongs and ask the user for it when showing the message. Omit the body for trivial changes such as typos.
   - Breaking changes: add `!` after the type or scope, and a `BREAKING CHANGE: <description>` footer.
4. Show the message to the user. Do not run `git commit` unless the user asks, and never run `git commit` while the message still contains a [WHY: ...] place holder.

## Commit types

Use only these types:
- feat: adds a user-facing feature or behavior.
- fix: corrects a bug.
- perf: improves performance without changing behavior. Use perf, not refactor, when speed is the main goal.
- refactor: restructures code without changing behavior or performance.
- docs: changes documentation only.
- test: adds or fixes tests only.
- chore: build, CI, dependencies, or tooling; no production code changes.
