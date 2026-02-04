# Skills Installation Guide

This document provides installation instructions and source URLs for all skills used in this workspace. Use this guide to reinstall skills when they become unavailable or need updating.

## Installed Skills Overview

| Skill | Description | Source |
|-------|-------------|--------|
| `docs-writer` | Documentation writing, reviewing, and editing | Google Gemini CLI |
| `notion-knowledge-capture` | Capture conversations into structured Notion pages | OpenAI Skills |
| `notion-meeting-intelligence` | Prep meetings with Notion context and tailored agendas | OpenAI Skills |
| `notion-research-documentation` | Research Notion content and produce briefs/reports | OpenAI Skills |
| `notion-spec-to-implementation` | Turn Notion specs into implementation plans and tasks | OpenAI Skills |

---

## Installation Instructions

### Prerequisites

Before installing skills, ensure the Notion MCP is properly configured (Codex example):

1. **Add the Notion MCP:**
   ```bash
   codex mcp add notion --url https://mcp.notion.com/mcp
   ```

2. **Enable remote MCP client:**
   - Set `[features].rmcp_client = true` in `config.toml`
   - Or run: `codex --enable rmcp_client`

3. **Log in with OAuth:**
   ```bash
   codex mcp login notion
   ```

---

## Skills Source URLs

### docs-writer (Google Gemini CLI)

**Repository:** [google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli)

**Source Files:**
- GitHub Tree: https://github.com/google-gemini/gemini-cli/tree/main/.gemini/skills/docs-writer
- Raw SKILL.md: https://raw.githubusercontent.com/google-gemini/gemini-cli/main/.gemini/skills/docs-writer/SKILL.md

**Install Location:** `.agent/skills/docs-writer/`

---

### notion-knowledge-capture (OpenAI)

**Repository:** [openai/skills](https://github.com/openai/skills)

**Source Files:**
- GitHub Tree: https://github.com/openai/skills/tree/main/skills/.curated/notion-knowledge-capture
- Raw SKILL.md: https://raw.githubusercontent.com/openai/skills/main/skills/.curated/notion-knowledge-capture/SKILL.md

**Install Location:** `.agent/skills/notion-knowledge-capture/`

**Purpose:** Capture conversations and decisions into structured Notion pages. Use when turning chats/notes into wiki entries, how-tos, decisions, or FAQs with proper linking.

---

### notion-meeting-intelligence (OpenAI)

**Repository:** [openai/skills](https://github.com/openai/skills)

**Source Files:**
- GitHub Tree: https://github.com/openai/skills/tree/main/skills/.curated/notion-meeting-intelligence
- Raw SKILL.md: https://raw.githubusercontent.com/openai/skills/main/skills/.curated/notion-meeting-intelligence/SKILL.md

**Install Location:** `.agent/skills/notion-meeting-intelligence/`

**Purpose:** Prepare meeting materials with Notion context and Codex research. Use when gathering context, drafting agendas/pre-reads, and tailoring materials to attendees.

---

### notion-research-documentation (OpenAI)

**Repository:** [openai/skills](https://github.com/openai/skills)

**Source Files:**
- GitHub Tree: https://github.com/openai/skills/tree/main/skills/.curated/notion-research-documentation
- Raw SKILL.md: https://raw.githubusercontent.com/openai/skills/main/skills/.curated/notion-research-documentation/SKILL.md

**Install Location:** `.agent/skills/notion-research-documentation/`

**Purpose:** Research across Notion and synthesize into structured documentation. Use when gathering info from multiple Notion sources to produce briefs, comparisons, or reports with citations.

---

### notion-spec-to-implementation (OpenAI)

**Repository:** [openai/skills](https://github.com/openai/skills)

**Source Files:**
- GitHub Tree: https://github.com/openai/skills/tree/main/skills/.curated/notion-spec-to-implementation
- Raw SKILL.md: https://raw.githubusercontent.com/openai/skills/main/skills/.curated/notion-spec-to-implementation/SKILL.md

**Install Location:** `.agent/skills/notion-spec-to-implementation/`

**Purpose:** Turn Notion specs into implementation plans, tasks, and progress tracking. Use when implementing PRDs/feature specs and creating Notion plans + tasks from them.

---

## Manual Reinstallation

To manually reinstall any skill:

1. **Clone the repository** (or download specific files):
   ```bash
   # For OpenAI skills
   git clone https://github.com/openai/skills.git
   cp -r skills/skills/.curated/notion-* .agent/skills/
   
   # For Gemini CLI docs-writer
   git clone https://github.com/google-gemini/gemini-cli.git
   cp -r gemini-cli/.gemini/skills/docs-writer .agent/skills/
   ```

2. **Or use curl to download specific files:**
   ```bash
   # Example for notion-knowledge-capture SKILL.md
   curl -o .agent/skills/notion-knowledge-capture/SKILL.md \
     https://raw.githubusercontent.com/openai/skills/main/skills/.curated/notion-knowledge-capture/SKILL.md
   ```

3. **Verify installation** by checking the skill is recognized in your agent configuration.

---

## Additional Resources

- [OpenAI Skills Catalog](https://github.com/openai/skills)
- [Google Gemini CLI Repository](https://github.com/google-gemini/gemini-cli)
