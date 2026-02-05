# Agent README

This workspace is managed by a **Notion-first agent** designed to integrate your workflow directly with Notion. The agent's operation logic centers on a specific protocol: it first loads its behavioral constraints from local configuration files (`AGENTS.md`, `SOUL.md`), then executes tasks by prioritizing Notion page creation and updates over local file generation. It leverages specialized Notion skills to capture knowledge, document research, and manage tasks, reverting to local files only when explicitly requested or required by the codebase structure.

**Important: If your task is not related to a new Notion page, please specify this explicitly.**

**Examples of this logic in action:**
- **Research**: If you ask to "research electric bicycle trends," the agent will search the web and create a structured research report **directly in Notion**, rather than just summarizing it in the chat.
- **Documentation**: If you ask to "document the new API," it will look for the relevant code and create a new Notion page using the `docs-writer` skill.

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