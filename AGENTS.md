# AGENTS.md

Use this file to define how Codex works in this workspace. It sets scope,
workflow, and verification rules so every task starts with the same
expectations.

## Authority files

This section identifies the files that define the agent's baseline behavior
and tool usage.

- `SOUL.md` defines core characteristics and operating principles.
- `TOOLS.md` defines capabilities, skill usage, and Notion structure rules.

## Scope and context

Codex works within the current workspace root unless you say otherwise. Keep
this scope tight to reduce risk and keep changes easy to review.

- Work only within the workspace root unless I ask you to go elsewhere.
- Treat network access as off unless I explicitly ask you to enable it.
- Ask for clarification when the request is ambiguous or required inputs are
  missing.

## Notion-first behavior

This workspace focuses on Notion writing. Use the Notion-related skills and
tools whenever the task touches Notion, and assume the goal is to create or
update a Notion note unless I explicitly say otherwise.

- Use the Notion skills to connect to Notion when writing or editing content.
- Assume the user wants a Notion note by default. If that assumption might be
  wrong, confirm before you proceed.
- Before writing to Notion, map the current Notion structure and identify the
  correct database or page. Do not change schema, properties, or database
  structure unless I explicitly request it.

## Notion skills

Use these skills when the task involves Notion.

- `notion-knowledge-capture`: Capture conversations and decisions into
  structured Notion pages with proper linking.
- `notion-meeting-intelligence`: Prepare meeting materials with Notion context
  and tailored agendas or pre-reads.
- `notion-research-documentation`: Research across Notion and synthesize into
  structured documentation with citations.
- `notion-spec-to-implementation`: Turn Notion specs into implementation plans,
  tasks, and progress tracking.

## Workflow

Follow this sequence so tasks stay predictable and reviewable.

1. Restate the goal and confirm any assumptions that affect the approach.
2. Inspect relevant files before editing.
3. Propose a brief plan for multi-step or risky work, and wait for approval if
   the plan changes scope or risk.
4. Make the smallest change that solves the task and follow existing patterns.
5. Summarize changes and list any tests you ran or explicitly note when you
   did not run tests.

## Changes and verification

Keep changes safe, minimal, and verifiable.

- Run relevant tests when a command exists and the scope warrants it.
- Don't add new dependencies without approval.
- Avoid destructive actions unless I explicitly request them.

## Communication

Keep updates concise and make it easy to audit what you changed.

- Use `code` formatting for commands, file paths, and important terms.
- Call out risks, limitations, or missing context before you proceed.

## Next steps

Update this file when workflows, tooling, or safety requirements change.

## Self-update template

Use this template when the user asks the agent to update its own guidance
files.

1. Change request: [one sentence]
2. Files to update: [`AGENTS.md`, `SOUL.md`, `TOOLS.md`]
3. Scope impact: [none | minor | moderate | major]
4. Proposed edits: [brief list of sections to change]
5. Verification: [tests run or "not run"]
