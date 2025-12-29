<!-- Short, actionable instructions for AI coding agents working in this repository -->
# Copilot instructions — Project snapshot

Purpose: Help AI coding agents be immediately productive in this tiny workspace.

Overview
- This repository currently contains a few simple text artifacts (no build system, tests, or language-specific source code).
- Key files discovered:
  - `Bootcamp/Test2` — small text file (contents: "test").
  - `test1/Demo` — small text file.
  - `test1/Demo 1` — small text file (note the space in the filename).

What the agent should assume
- No automated CI, build scripts, or package manifests were found. Confirm with the user before creating or running scripts.
- Paths may include spaces (e.g., `test1/Demo 1`) — when constructing shell commands, quote paths.

Primary goals for the agent
- Make minimal, well-explained edits the user requests (small content changes, file renames, or adding simple files).
- When asked to add code or tests, propose a minimal runnable plan and confirm language/runtime before scaffolding.

Conventions and patterns (repo-specific)
- Keep changes small and local: modify only files the user explicitly asked about unless they ask for broader refactors.
- Use `apply_patch` style edits (patched diffs) for changes; include concise commit-style messages in PRs.
- Preserve filename spacing and casing; if renaming `Demo 1`, confirm desired new name first.

Developer workflows (discoverable)
- No `package.json`, `pyproject.toml`, or Makefile found — there are no standard build/test commands to run.
- Use Git for edits: create a short-lived branch `update/<desc>` and a descriptive commit message like "edit: update Demo text — <reason>".

Integration points & external dependencies
- None detected. If the user asks to add integrations (CI, package manager, remote services), present a short plan and required files.

Examples (how to make common edits)
- Update a small file content (preferred): edit `Bootcamp/Test2` to the exact new text the user requested.
- Rename safely: to rename `test1/Demo 1` → `test1/Demo-1`, propose the change and run `git mv` (confirm first).

Safety & verification
- Do not execute unknown scripts. If asked to run commands, show the exact commands and ask for confirmation.
- When adding executable code, provide a minimal README and a one-line test command for the user to run locally.

When in doubt
- Ask a clarifying question before making non-trivial changes (new languages, CI, or service integrations).

If this file is outdated
- Merge any local agent guidance into this file preserving explicit examples and any workflow commands.

Ready for review — ask the user what to do next.
