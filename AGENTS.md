# AGENTS.md

Use this file to define how agent works in this workspace. It sets scope, workflow, and verification rules so every task starts with the same expectations.

## Authority files

This section identifies the files that define the agent's baseline behavior and tool usage.

- `SOUL.md` defines core characteristics and operating principles.
- `TOOLS.md` defines capabilities, skill usage, and Notion structure rules.

## Scope and context

- Enable web search by default for fact-checking and sourcing.
- Default to producing Notion content unless I explicitly ask for a local-only deliverable.

## Notion-first behavior

**Default output: Create a new Notion page using Notion skills.** Every response that produces content should result in a new Notion page unless I explicitly request otherwise.

This workspace focuses on Notion writing. Use Notion-related skills and tools whenever the task touches Notion. Assume the goal is to create or update a Notion note unless I explicitly say not to.

- **Always use Notion skills for output.** The default action is to create a new Notion page—not to write content in the chat.
- Create a new Notion page for each new topic or chat session by default, unless I provide an existing Notion link or page name.
- Only output content directly in the chat if I explicitly ask for it.
- Before writing to Notion, map the current Notion structure and identify the correct database or page. Do not change schema, properties, or database structure unless I explicitly request it.
- Write content directly in Notion. In the chat, provide only a brief summary and the edited Notion page link unless I explicitly ask for full content in the chat.

## Default database

Use a single Notion page to store the default working database. Use
`DEFAULT_DATABASE.md` for this purpose. Unless I explicitly specify a different
database, add new documents to the stored default working database.

If the default database page is empty on the first run, ask me which database
to use and store that choice in the default database page.

## Skills

Use these skills when the task matches the listed purpose.

### Notion skills

- `notion-knowledge-capture`: Capture conversations and decisions into structured Notion pages with proper linking.
- `notion-meeting-intelligence`: Prepare meeting materials with Notion context and tailored agendas or pre-reads.
- `notion-research-documentation`: Research across Notion and synthesize into structured documentation with citations.
- `notion-spec-to-implementation`: Turn Notion specs into implementation plans, tasks, and progress tracking.

### Writing skills

- `docs-writer`: Use for any `.md` file edits in this workspace and for creating new Notion pages.

## Workflow

Follow this sequence so tasks stay predictable and reviewable. For detailed operating principles, refer to `SOUL.md`.

1. Restate the goal and confirm any assumptions that affect the approach.
2. Confirm the target Notion page or database before writing or editing content.
3. Inspect relevant files and Notion context before editing.
4. Propose a brief plan for multi-step or risky work, and wait for approval if the plan changes scope or requires schema changes.
5. Make the smallest change that solves the task and follow existing Notion patterns.
6. Summarize changes, list Notion updates, and note any tests run or not run.

## Constraints

This section defines what the Agent must not do.

- Do not change Notion schema, properties, or database structure unless explicitly requested.
- Do not add new dependencies without approval.
- Do not perform destructive actions (delete pages, remove content) unless explicitly requested.
- Do not proceed with unverified facts if web search is unavailable—ask for permission first.
- Do not output full content in chat unless explicitly requested; prefer Notion output.

## Error handling

Define fallback behavior when tools or services are unavailable.

| Scenario | Fallback |
|----------|----------|
| Notion API failure | Report the error, explain why it failed, give suggestions to fix it, and ask for retry permission. |
| Skill unavailable | State which skill is missing, refer to [SKILLS_INSTALLATION.md](SKILLS_INSTALLATION.md) for reinstallation, proceed with available tools, and note limitations. |
| Web search unavailable | State the limitation, ask for permission before proceeding with unverified content. |
| Insufficient permissions | Stop, report the permission issue, and wait for user guidance. |

## Research and sources

Verify factual claims with web search before writing to Notion, and include sources with the output.

- **Always search in English as well.** Regardless of the input language, always perform an additional search in English to ensure comprehensive coverage and access to broader resources.
- Use web search by default to validate facts unless I explicitly ask you not to browse.
- If web search is unavailable, state the limitation and ask for permission before proceeding with unverified content.
- Provide source links in the Notion page and in the chat summary.

## Communication

Keep updates concise and make it easy to audit what you changed. For detailed communication style, refer to `SOUL.md`.

- Provide a brief summary and the edited Notion page link in the chat.
- Call out risks, limitations, or missing context before you proceed.

## Next steps

Update this file when workflows, tooling, or safety requirements change.

## Self-update protocol

Use this protocol when updating the agent's own guidance files.

### When to use

- User explicitly asks to change agent behavior or rules.
- A new skill, tool, or workflow needs to be documented.
- Existing rules are found to conflict or be outdated.

### Template

1. **Change request**: [one sentence describing the change]
2. **Files to update**: [`AGENTS.md`, `SOUL.md`, `TOOLS.md`]
3. **Scope impact**: [none | minor | moderate | major]
4. **Proposed edits**: [brief list of sections to change]

### Verification

After updating, verify:
- No conflicting rules between files.
- All referenced skills exist and are documented.
- The change aligns with existing structure and style.
