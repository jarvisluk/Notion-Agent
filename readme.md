# Agent README

This workspace is configured for a Notion-first Codex agent. Use this document to understand the agent's defaults, how to make requests, and what you can customize.

## Customize the agent (start here)

You customize this agent by editing the workspace guidance files. Keep changes small and reviewable.

- `AGENTS.md`: Workflow, scope, Notion-first rules, research policy, and verification expectations.
- `SOUL.md`: Identity, operating principles, communication style, and how the guidance files get updated.
- `TOOLS.md`: Tooling constraints, skill usage rules, and default Notion structure expectations.

Common customizations:

- **Scope**: Change where the agent is allowed to read and write.
- **Notion-first behavior**: Decide when the agent should write to Notion versus drafting locally.
- **Research policy**: Require web verification (or explicitly disable it) for factual claims and citations.
- **Verification**: Set when the agent must run tests or other checks.
- **Output format**: Specify how you want results delivered (for example, "Notion page only," "local Markdown only," or "both").

If you want the agent to update its own guidance, ask explicitly and use the "Self-update template" section in `AGENTS.md`.

## What this agent is for

This agent defaults to writing and organizing content for Notion, then keeping local workspace artifacts (notes, drafts, scripts) small and easy to audit.

## Default workflow

The agent follows a predictable workflow for most tasks.

1. Restate the goal and confirm assumptions.
2. Confirm the target Notion page or database before writing to Notion.
3. Inspect relevant files and context before editing.
4. Propose a brief plan for multi-step or risky work.
5. Make the smallest change that solves the task.
6. Summarize what changed and what was verified.

## Notion work (expected inputs)

For Notion-related tasks, provide at least one of the following so the target is unambiguous.

- A Notion page link, page name, or database name.
- The intended page type (note, article, decision record, meeting agenda).
- Any required properties (status, tags, owner, date).

If the target is ambiguous or missing, the agent asks clarifying questions before writing. If Notion connectivity is unavailable in this environment, the agent drafts content locally in Markdown so you can paste it into Notion.

## Tooling and safety defaults

This workspace is optimized for safe, minimal, and verifiable changes.

- Network access is treated as off unless you explicitly request it.
- The agent avoids destructive actions unless you explicitly request them.
- The agent does not add dependencies unless you explicitly approve it.
- When a relevant test or check exists and the scope warrants it, the agent runs it and reports the result (or notes that it was skipped).

## Where to look for the rules

If behavior is surprising, check these files first.

- `AGENTS.md`: Primary workflow and Notion-first policy.
- `SOUL.md`: Stable behavior and communication rules.
- `TOOLS.md`: Tool usage and Notion structure conventions.
