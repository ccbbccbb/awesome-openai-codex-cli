<div align="center">
<img src="assets/openai-logo.png" alt="OpenAI Logo" width="140">
<h1 align="center">Awesome OpenAI Codex CLI</h1>
<p align="center">
  <a href="https://awesome.re">
    <img src="https://awesome.re/badge.svg" alt="Awesome">
  </a>
  <a href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="https://img.shields.io/badge/License-CC0_1.0-white.svg" alt="License: CC0-1.0">
  </a>
</p>
<p align="center">
  <b>A curated list of awesome OpenAI Codex CLI resources, integrations, & tools.</b>
  <br>Official Codex CLI repository with additional info <a href="https://github.com/openai/codex">can be found here.</a>
</p>
</div>

```
  ┌────────────────────────── Awesome OpenAI Codex CLI ────────────────────────────┐             
  │                                                                                │
  │   $ codex "make some ASCII art for my README.md file"                          │
  │                                                                                │
  │   $ codex "get me a link to the codex cli repo"                                │
  │   > Here's a link to the codex cli repo: https://github.com/openai/codex       │                         
  │                                                                                │
  │   $ _                                                                          │
  │                                                                                │
  └────────────────────────────────────────────────────────────────────────────────┘
```

## Table of Contents

- [Introduction](#introduction)
  - [TLDR](#tldr)
  - [What does Codex do?](#what-does-codex-do)
- [Installation](#installation)
  - [Method A](#method-a)
  - [Method B](#method-b)
  - [CLI Examples](#cli-examples)
  - [Quick Start Examples](#quick-start-examples)
  - [Automation Modes](#automation-modes)
  - [CLI Parameters](#cli-parameters)
- [Dive Deeper](#dive-deeper)
- [Best of OpenAI Cookbook](#best-of-openai-cookbook)
- [Codex Architecture](#codex-architecture)
- [Tips and Tricks](#tips-and-tricks)
  - [Advanced Features](#advanced-features)
  - [CLI Prompt Tips](#cli-prompt-tips)
  - [Prerequisites](#prerequisites)
  - [Shell Integration](#shell-integration)
- [Prompting Guide](#prompting-guide)
  - [Patterns](#patterns)
  - [Custom Instructions](#custom-instructions)
  - [More Examples](#more-examples)
- [Common Questions](#common-questions)
  - [Troubleshooting Guide](#troubleshooting-guide)
  - [New Features & Integrations](#new-features--integrations)
  - [Future Coverage](#future-coverage)
- [Further Meaningful Reading](#further-meaningful-reading)
- [Contributing](#contributing)
- [Community](#community)
- [License](#license)
- [Credits](#credits)

## Introduction

### **TLDR – natural language prompting codex in your terminal**
 
Use simple prompts to set tasks in your terminalsuch as:
 
    `codex 'write unit tests for utils/date.ts'` 

### What does Codex do?

Codex CLI uses the model of your choice, plans the edits, runs code in a sandbox, shows diffs, and lets you approve. 

- You can even let it run in **full-auto mode**. 

- Zero setup beyond installing the CLI and exporting `OPENAI_API_KEY`.


## Installation

Codex CLI can be installed globally via npm, yarn, pnpm, or bun on MacOS and Linux:

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

### **Method A • Permanent export in** `~/.zshrc` **or** `~/.bashrc`
```bash
export OPENAI_API_KEY="sk-proj-..."
```
***Effect:** Every new shell session (and any program you launch from it) will have this variable, but your key is potentially exposed (someone please correct this statement if we are being too paranoid).*

### **Method B • One-off inline invocation**

Apply the key only to **codex** across all sessions without exposing it elsewhere, wrap it in an alias in your shell:

  ```bash
  alias cod3x='OPENAI_API_KEY="sk-proj-..." codex'
  ```

***Effect:** `cod3x` is the only way to invoke `codex` with your key, and no other process will inherit it.*

### Additional Codex CLI Examples

- [OpenAI Codex CLI Examples](https://github.com/openai/codex/tree/main/codex-cli/examples) - Example usage of the OpenAI Codex CLI

**Quick Start Examples**
  - [camerascii](https://github.com/openai/codex/tree/main/codex-cli/examples/camerascii) - Turn webcam feed into ASCII art
  - [build-codex-demo](https://github.com/openai/codex/tree/main/codex-cli/examples/build-codex-demo) - Recreate the 2021 Codex demo
  - [impossible-pong](https://github.com/openai/codex/tree/main/codex-cli/examples/impossible-pong) - Create challenging game levels
  - [prompt-analyzer](https://github.com/openai/codex/tree/main/codex-cli/examples/prompt-analyzer) - Build a prompt clustering app

### Automation Modes

| Mode      | Purpose                                                                                                    |
|---------------------|-------------------------------------------------------------------------------------------------------------|
  | `suggest` | Default - read-only; every file write & shell cmd needs approval                                                     |
| `auto-edit`        | File writes auto-approved; shell cmds still prompt                                                          |
| `full-auto`        | Files + shell cmds auto-run in sandbox (no network) 

### CLI Parameters

| CLI Parameter                  | Purpose                                                                                                    |
|---------------------|-------------------------------------------------------------------------------------------------------------|
| `--model`        | Default: `o4-mini`. Set model (`o4-mini`, `gpt-4.1-nano` etc.) ***Note:** Must be a model compatible with Responses API*.                                                                      |
| `--quiet`        | Non-interactive, minimal output                                                                             |
| `--json`             | Emit machine-readable JSON log                                                                              |


***TODO**: Ensure the above is kept up to date with the latest CLI docs.*


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

## Codex Architecture

How does Codex CLI tick under the hood? A lightning‑tour for power users:

- **Entry Point (`cli.tsx`)**: Parses CLI args, loads config, then boots the React‑based TUI.
- **Agent Loop (`agent-loop.ts`)**: Core brain that streams model responses, interprets function calls (file writes, shell exec), and enforces approval policy.
- **Sandbox Layer (`sandbox/`)**: macOS Seatbelt or Linux Docker/landlock jail; blocks network, restricts FS writes, kills rogue processes, and implements strict security policies including buffer limits and process group management for safe command execution.
- **Approval System**: Three modes you saw above; governed by an enum (`ApprovalPolicy`) so you can add custom policies.
- **Streaming & Cancellation**: Uses AbortController to cancel long‑running tool calls (hit ⎋ twice) – see PR #178 for recent bug‑fix.

For more low level details, dig into `openai-codex-cli/src/cli.tsx`.

## Tips and Tricks

Using a dedicated `.codex/` folder is a handy convention:
- Drop a high‑level requirements doc there and ask Codex to keep dated plan/README changelog files as it works. 
- The directory isn't magical to the CLI, but it gives you and the agent a shared scratchpad for milestones and progress tracking.

### Prerequisites
- Node.js v22 or higher
- An OpenAI API key with access to appropriate models
- For macOS/Linux: Terminal with bash/zsh
- For Windows: WSL2 recommended (untested by author)

### Shell Integration
Add to your `.bashrc` or `.zshrc` for command completion:
```bash
# For bash
eval "$(codex completion bash)"
# For zsh
eval "$(codex completion zsh)"
```

***TODO**: Debug evals, does not work for author.*

### Advanced Features
- **Command Chaining**: Chain complex workflows using pipes:
  ```bash
  codex "Write a script to parse CSV data" | codex "Add error handling to this script"
  ```
- **Image Support**: Include images in prompts for visual context:
  ```bash
  codex -i screenshot.png "Explain what's wrong with this UI"
  ```
- **Debug Mode**: Enable verbose logging for troubleshooting:
  ```bash
  DEBUG=1 codex "your prompt"
  tail -f "$TMPDIR/oai-codex/codex-cli-latest.log"
  ```
*Ripped from [OpenAI Codex CLI Examples](https://github.com/openai/codex/tree/main/codex-cli/examples).*

### CLI Prompt Tips
- Specify file paths relative to current working directory (`pwd`)
- Request shell commands explicitly (e.g., "run git diff", "execute npm install")
- Provide context from relevant files using shell commands within prompts
- Define desired output format clearly (e.g., "output a patch file", "generate JSON")

**TODO: Performance Optimization**
- Token efficiency 
- Memory management 
- Model selection trade-offs
- Response streaming optimization

**TODO: Configuration & Environment**
- Proxy configuration
- Advanced API key management
- Layered instruction files system
- Context window management

**TODO: MCP & Agent Framework Support**
- Tool calling
- Function calling
- Chain of thought prompting


### Integration Examples
- [OpenAI Codex CLI Examples](https://github.com/openai/codex/tree/main/codex-cli/examples) - Official examples including webcam ASCII art, Pong game, and prompt analysis tools
- **TODO**: Add more integration examples for:
  - Shell integration (command completion)
  - CI/CD pipeline integration
  - Git hooks integration

## Prompting Guide

**Note:** Mostly takeaways from [prompting_guide.md](https://github.com/openai/codex/blob/main/codex-cli/examples/prompting_guide.md) in OpenAI's Codex CLI Repo.

### Patterns
1. **Small Requests**: Pin‑point a single file/func.

   ```bash
   codex "Fix the regex in utils/validate.ts"
   ```
2. **Medium Tasks**: Pipe a markdown description:

   ```bash
   codex "$(cat task.md)"
   ```
3. **Large Projects**: Drop a roadmap in `.codex/` and run `--full-auto`.

### Custom Instructions
- Global: `~/.codex/instructions.md`  
- Project: `CODEX.md` at repo root

## More Examples

- [OpenAI API Quickstart](https://platform.openai.com/docs/guides/code) - Official quickstart guide for using the OpenAI API
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference/) - Technical reference for the API
- [OpenAI Prompt Examples](https://platform.openai.com/examples) - Example code generation use cases

## Common Questions

- [OpenAI Codex CLI Issues](https://github.com/openai/codex/issues) - Open issues and feature requests for the Codex CLI
- More to come.

**TODO: Troubleshooting Guide**
- Common issues and solutions
- Debugging instructions
- Error handling approaches

## New Features & Integrations

Highlights of bleeding-edge PRs in the upstream repo can be found in [PR-TRACKING.md](PR-TRACKING.md).

**TODO**: Push workflow we use via `mcp.json` file with `npx` (stdio mode) for tracking interesting PRs once integrated into the CLI. See [PR-TRACKING.md](PR-TRACKING.md) for details.

**TODO: Future Coverage**
- IDE integration possibilities
- Enhanced workflow automation
- Multi-model selection features
- Observability and logging improvements

## Further Meaningful Reading

- [Machines of Loving Grace](https://www.darioamodei.com/essay/machines-of-loving-grace) - Dario Amodei

## Contributing

Read the [contribution guidelines](CONTRIBUTING.md) first.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-codex-cli-feature`)
3. Commit your changes (`git commit -m 'Add some codex cli update or feature'`)
4. Push to the branch (`git push origin feature/amazing-codex-cli-feature`)
5. Open a Pull Request

## Community
• **[OpenAI Developer Forum](https://community.openai.com/)** – Official hub for technical discussions, implementation questions, and announcements about Codex CLI and other OpenAI tools.

• **[r/OpenAI Subreddit](https://www.reddit.com/r/OpenAI/)** – Community-driven space for sharing experiences, tips, and discussing OpenAI's latest developments.

**TODO**: Add more community links (X Dev Account, etc.)

## License

This repository is distributed under the [CC0 1.0 Universal](LICENSE) license, following best practices for "awesome" lists (e.g., awesome-machine-learning). For details, see [LICENSE](LICENSE).

---

## Credits

Work in progress. Curated with intent.