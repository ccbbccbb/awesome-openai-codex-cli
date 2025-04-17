# awesome-openai-codex-cli 

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

#### A curated list of awesome resources, tools, applications, and documentation for OpenAI's Codex CLI

## Table of Contents

1. [Quick Start](#quick-start)
2. [Getting Started](#getting-started)
3. [Integrations Showcase](#integrations-showcase)
4. [Best of OpenAI Cookbook](#best-of-openai-cookbook)
5. [Guides & Examples](#guides-examples)
6. [Common Questions](#common-questions)
7. [Contributing](#contributing)
8. [PR Tracking](#pr-tracking)
9. [License](#license)

## Quick Start

- [OpenAI Codex CLI](https://github.com/openai/codex) - Official repository for the Codex CLI
- [OpenAI Codex CLI Examples](https://github.com/openai/codex/tree/main/codex-cli/examples) - Examples for the OpenAI Codex CLI

 #### **TL;DR – natural language codex in your terminal**
 
 Use natural‑language to set tasks such as:
 
 `codex "Write unit tests for utils/date.ts"` 
 
 Codex CLI plans the edits, runs code in a sandbox, shows diffs, and lets you approve (or let it run in **auto** modes). Zero setup beyond installing the CLI and exporting `OPENAI_API_KEY`.

## Getting Started

**Installation:** Codex CLI can be installed globally via npm, yarn, pnpm, or bun:

```bash
# via npm:
npm install -g @openai/codex
# via yarn:
yarn global add @openai/codex
# via pnpm:
pnpm add -g @openai/codex
# via bun:
bun add -g @openai/codex
```

> **Note:** `pnpm` is not officially recommended or tested by upstream docs; `bun` has been tested and works for global installs for the author of this repo.

**Method 1 • Permanent export in** `~/.zshrc` **or** `~/.bashrc`
```bash
export OPENAI_API_KEY="sk-proj-..."
```
***Effect:** Every new shell session (and any program you launch from it) will have this variable, but your key is potentially exposed (someone please correct this statement if we are being too paranoid).*

**Method 2 • One-off inline invocation**

Apply the key only to **codex** across all sessions without exposing it elsewhere, wrap it in an alias in your shell:

  ```bash
  alias cod3x='OPENAI_API_KEY="sk-proj-..." codex'
  ```

***Effect:** `cod3x` is the only way to invoke `codex` with your key, and no other process will inherit it.*

### Automation Modes

| Mode      | Purpose                                                                                                    |
|---------------------|-------------------------------------------------------------------------------------------------------------|
| `suggest` | Default - read-only; every file write & shell cmd needs approval                                                     |
| `auto-edit`        | File writes auto-approved; shell cmds still prompt                                                          |
| `full-auto`        | Files + shell cmds auto-run in sandbox (no network) 

| Codex CLI Parameter                  | Purpose                                                                                                    |
|---------------------|-------------------------------------------------------------------------------------------------------------|
| `--model`        | Default: `o4-mini`. Set model (`o4-mini`, `gpt-4.1-nano` etc.) ***Note:** Must be a model compatible with Responses API*.                                                                      |
| `--quiet`        | Non-interactive, minimal output                                                                             |
| `--json`             | Emit machine-readable JSON log                                                                              |

## Dive Deeper

- [OpenAI Codex CLI Announcement](https://community.openai.com/t/this-weeks-launches-o3-o4-mini-gpt-4-1-and-codex-cli/1230312)  OpenAI Forum post covering Codex CLI announcement + o3 + o4 mini release
- [Introducing GPT-4.1 in the API](https://openai.com/index/gpt-4-1/) Announcement of GPT-4.1, GPT-4.1-mini, and GPT-4.1-nano
- [OpenAI Responses API x Agents Announcement](https://openai.com/index/new-tools-for-building-agents/) - Introduction of Responses API, Web Tools, Agent SDK, and building block roadmap hints
- [OpenAI Codex Open Source Fund](https://openai.com/form/codex-open-source-fund/) - Apply for $25,000 in API Credits

## Best of OpenAI Cookbook
Curated information covering most relevant info for OpenAI Codex CLI.

- [GPT-4.1 Prompting Guide](https://cookbook.openai.com/examples/gpt4-1_prompting_guide) (April 14th, 2025) - Tips and best practices for prompt engineering with GPT-4.1, covering agentic workflows, tool-calling, chain-of-thought, and long context handling.
- [Responses API: Tool Orchestration](https://cookbook.openai.com/examples/responses_api/responses_api_tool_orchestration) (March 28th, 2025) - Guide on orchestrating multiple tools using the Responses API, including design patterns and code examples.
- [Responses Example](https://cookbook.openai.com/examples/responses_api/responses_example) (March 11th, 2025) - Basic example demonstrating how to use the Responses API to call functions and handle responses.
- [File Search Responses](https://cookbook.openai.com/examples/file_search_responses) (March 11th, 2025) - Example showcasing file search capabilities and response handling with the Responses API.

## Guides & Examples

- [OpenAI API Quickstart](https://platform.openai.com/docs/guides/code) - Official quickstart guide for using the OpenAI API
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference/) - Technical reference for the API
- [OpenAI Prompt Examples](https://platform.openai.com/examples) - Example code generation use cases

## Common Questions

- [OpenAI Codex CLI Issues](https://github.com/openai/codex/issues) - Open issues and feature requests for the Codex CLI
- More to come.

## Recent Features & Integrations

Highlights of bleeding-edge PRs in the upstream repo can be found in [PR-TRACKING.md](PR-TRACKING.md).

**TODO**: Push workflow we use via `mcp.json` file with `npx` (stdio mode) for tracking interesting PRs once integrated into the CLI. See [PR-TRACKING.md](PR-TRACKING.md) for details.

## Further Meaningful Reading

- [Machines of Loving Grace](https://www.darioamodei.com/essay/machines-of-loving-grace) by Dario Amodei (CEO of Anthropic)

## Contributing

Your contributions are always welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-codex-cli-feature`)
3. Commit your changes (`git commit -m 'Add some codex cli update or feature'`)
4. Push to the branch (`git push origin feature/amazing-codex-cli-feature`)
5. Open a Pull Request

## License

This repository is distributed under the [CC0 1.0 Universal](LICENSE) license, following best practices for "awesome" lists (e.g., awesome-machine-learning). For details, see [LICENSE](LICENSE).

---

## Credits

Curated with ❤️ by the community (with a subtle nod to SD and LP7)

- #F7EE49
- #4686C6
- #F36525
- #45B64A
- #EDB41F
- #EC2427
- #A4DDE6