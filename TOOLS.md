# TOOLS.md

This file documents the agent's capabilities, skill usage rules, and Notion structure expectations.

## Tooling rules

This section defines how tools are selected and used.

- Treat network access as off unless the user explicitly requests it.
- Use `rg` for search when possible.
- Use `apply_patch` for single-file edits when it is the safest choice.
- Do not add dependencies without explicit approval.

## Skill usage

This section defines when to load skills.

- Use Notion skills when a task touches Notion content or structure.
- Use `docs-writer` for any `.md` edits in this workspace.
- If multiple skills apply, use the minimal set and state the order.

## Notion structure

This section defines how to discover or initialize Notion structure.

### Discovery protocol

Start by mapping the current Notion structure and identifying the target workspace, database, or page.

- If a target database already exists, follow its schema and conventions.
- Do not change schema or properties unless explicitly requested.

### Default database when empty

If the target Notion workspace or page is empty, create a sample "Article storage" database with the following properties.

- `Title` (title)
- `Status` (select: `Idea`, `Draft`, `Review`, `Published`)
- `Type` (select: `Essay`, `Note`, `Reference`, `Summary`)
- `Tags` (multi-select)
- `Author` (text)
- `Source` (select: `Original`, `External`)
- `Source URL` (url)
- `Published date` (date)
- `Summary` (text)
- `Notes` (text)
- `Created` (created time)
- `Last edited` (last edited time)
