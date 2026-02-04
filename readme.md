# Agent README

This workspace is configured for a Notion-first agent. Use this document to understand the agent's defaults, how to make requests, and what you can customize.

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