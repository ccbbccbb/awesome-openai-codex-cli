# PR-TRACKING.md

This file documents **how we grab interesting pull requests from the upstream `openai/codex` repository using `mcp.json` + `npx`** so we can keep an eye on potential new features.

### **Cursor Workflow (similar workflow for VSCode)**

**Step 1** • Add `mcp.json` to the repo root (works):

  ```json
  {
    "mcpServers": {
      "github": {
        "command": "npx",
        "args": [
          "-y",
          "@modelcontextprotocol/server-github"
        ]
      }
    }
  }
  ```

**Step 2** • Enable the `mcp` extension in Cursor settings and open up Agent mode with a query to pull all relevant PR's upstream from `openai/codex`.


## Codex CLI Main Repo Tracking Table

| PR # | Title                                             | Status | Link |
|------|---------------------------------------------------|--------|------|
| 186 | fix: add missing *as* in prompt prefix | open | https://github.com/openai/codex/pull/186 |
| 185 | feat: experimental side‑by‑side diff mode | open | https://github.com/openai/codex/pull/185 |
| 160 | feat: add notifications for macOS | open | https://github.com/openai/codex/pull/160 |
| 163 | feat: securely store api keys | open | https://github.com/openai/codex/pull/163 |
| 173 | feat: shell command explanation option | open | https://github.com/openai/codex/pull/173 |
| 172 | feat: platform-specific directory support | open | https://github.com/openai/codex/pull/172 |
| 176 | feat: graceful backoff on rate limits | open | https://github.com/openai/codex/pull/176 |
| 92  | feat: Azure OpenAI support | open | https://github.com/openai/codex/pull/92 |
| 75  | feat: open router model support | open | https://github.com/openai/codex/pull/75 | 