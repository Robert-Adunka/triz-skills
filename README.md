# TRIZ Skills

TRIZ methodology skills for use with Claude and ChatGPT via MCP Server.

Each skill folder contains a `SKILL.md` with the methodology guide, and optionally a `references/` folder with supporting material (matrices, principles, examples).

## Available Skills

| Folder | Description |
|---|---|
| `76-standard-solutions` | 76 Standard Solutions |
| `business-function-analysis` | Business Function Analysis |
| `cause-effect-chain-analysis` | Cause-Effect Chain Analysis |
| `contradiction-solver` | Contradiction Solver (Altshuller Matrix + Matrix 2003) |
| `derivative-resources` | Derivative Resources |
| `feature-transfer` | Feature Transfer |
| `function-analysis` | Function Analysis |
| `function-analysis-advanced` | Advanced Function Analysis |
| `function-interaction-analysis` | Function Interaction Analysis |
| `function-oriented-search` | Function-Oriented Search |
| `ideality` | Ideality |
| `innovation-checklist` | Innovation Checklist |
| `interactive-trimming` | Interactive Trimming |
| `mpv-analysis` | MPV Analysis |
| `patent-analyzer` | Patent Analyzer |
| `perception-mapping` | Perception Mapping |
| `physical-contradictions` | Physical Contradictions |
| `problem-operator` | Problem Operator (Problem-Oriented Nine Screen Approach) |
| `resource-analysis` | Resource Analysis |
| `root-cause-analysis` | Root Cause Analysis |
| `root-conflict-analysis` | Root Conflict Analysis (RCA+) |
| `smart-little-people` | Smart Little People |
| `solutions-at-system-levels` | Solutions at System Levels |
| `sustainability-assessment` | Sustainability Assessment |
| `system-description` | System Description |
| `system-operator` | System Operator (Multi-Screen Diagram) |
| `trimming` | Trimming |

## MCP Server Setup

These skills are served via an n8n MCP Server at:

```
https://n8n.triz-consulting.de/mcp/triz-skills
```

### Claude Code (Terminal)

Run once in your terminal:

```bash
claude mcp add triz-skills --transport http https://n8n.triz-consulting.de/mcp/triz-skills \
  --header "Authorization: Bearer ba160317c033f6d76f2f4bc4645760f0ccae214671c3fa21e530d5b5b4276cd4" \
  --scope user
```

Verify the connection:

```bash
claude mcp list
```

`triz-skills` should appear with `✓ Connected`.

### Claude Code (Web)

Open [claude.ai/code](https://claude.ai/code), then:

1. Click **Customize** (below the chat input)
2. Select the **Connectors** tab
3. Click **+** (top right) to add a new connector
4. Fill in:
   - **Name:** `TRIZ Skills`
   - **Remote MCP Server URL:** `https://n8n.triz-consulting.de/mcp/triz-skills-web`
   - **Authentication:** **No authentication** (claude.ai marks it as *Detected*)
5. Click **Add**

The skills appear immediately — no restart required.

> **Do not choose "Sign in now" or "Sign in when needed".** The endpoint needs no login. With an OAuth option selected, claude.ai tries to sign in against n8n's own OAuth server, which rejects it with `{"error":"invalid_target","error_description":"Resource is not available for authorization"}`. If an existing connector shows this error, delete it and add it again with **No authentication**.

### Claude Desktop

Open `~/Library/Application Support/Claude/claude_desktop_config.json` (Mac) or `%APPDATA%\Claude\claude_desktop_config.json` (Windows) and add the following to the `mcpServers` block:

```json
"triz-skills": {
  "command": "npx",
  "args": [
    "-y",
    "mcp-remote",
    "https://n8n.triz-consulting.de/mcp/triz-skills",
    "--header",
    "Authorization: Bearer ba160317c033f6d76f2f4bc4645760f0ccae214671c3fa21e530d5b5b4276cd4"
  ]
}
```

Then restart Claude Desktop. The skills appear under the 🔨 tools icon in the chat.

### ChatGPT Desktop

Open **Plugins** (Plugins, Skills und MCPs verwalten), then:

1. Select the **MCPs** tab and click **Add**
2. Fill in:
   - **URL:** `https://n8n.triz-consulting.de/mcp/triz-skills`
   - **Bearer token environment variable:** leave **empty**
   - **Headers** → **+ Add header**:
     - Key: `Authorization`
     - Value: `Bearer ba160317c033f6d76f2f4bc4645760f0ccae214671c3fa21e530d5b5b4276cd4`
3. Click **Save** and start a new chat

Ask ChatGPT which `triz_*` tools it sees. All should be listed.

> **Do not paste the token into "Bearer token environment variable".** That field expects the *name* of an environment variable, not the token. If it holds the token, ChatGPT reports that the configuration references an unset environment variable and does not start the server.

### Requirements

- Node.js must be installed (`node --version` to check) → https://nodejs.org
- Claude Code ≥ 1.0 or Claude Desktop (current version)
- ChatGPT: no Node.js needed

### Usage

Just ask naturally — Claude selects the right skill automatically:

> *"I want to do a function analysis of my electric toothbrush."*

> *"Let's analyze the smartphone using the System Operator."*

> *"Help me find the root cause of this manufacturing defect."*

## License

Copyright (c) 2026 Robert Adunka. Based on original TRIZ methodology prompts by Jens Träger.
Licensed under the MIT License — see [LICENSE](LICENSE) in the repository root.
