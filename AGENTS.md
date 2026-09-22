# qwen-code-agents — Qwen Code adaptation of the claude-agents marketplace

Production-ready agentic-workflow building blocks: **94 plugins** (92 local + 2 external), **202 agents**, **183 skills**, **105 commands**, adapted for [Qwen Code](https://qwenlm.github.io/qwen-code-docs/en/).

This repository is a **fork/adaptation** of [wshobson/agents](https://github.com/wshobson/agents) by [Seth Hobson](https://github.com/wshobson). All original plugin content, agent expertise, skill knowledge, and command workflows are his work. This adaptation wires that content to Qwen Code's extension format.

If you are an agent working in this repo, read this file first; it is the canonical context file.

## Map

- **[README.md](README.md)** — user-facing overview, install steps, model-tier strategy
- **[QWEN-SETUP.md](QWEN-SETUP.md)** — step-by-step Qwen Code setup
- **[docs/plugins.md](docs/plugins.md)** — full plugin catalog (92 plugins by category)
- **[docs/agents.md](docs/agents.md)** — agent reference (202 agents, model tiers)
- **[docs/agent-skills.md](docs/agent-skills.md)** — skill reference (progressive disclosure model)
- **[docs/usage.md](docs/usage.md)** — commands, workflows, examples
- **[docs/architecture.md](docs/architecture.md)** — design principles
- **[docs/plugin-eval.md](docs/plugin-eval.md)** — three-layer quality evaluation framework
- **[CONTRIBUTING.md](CONTRIBUTING.md)** — upstream contribution guide

## What this fork changes

Upstream ships to seven harnesses (Claude Code, Codex, Cursor, OpenCode, Antigravity, Copilot, Pi) from one Markdown source, using a generator + adapter framework under `tools/`. **This fork does not carry that framework.** It applies a fixed, mechanical adaptation instead:

| Change | Detail |
| --- | --- |
| `model:` aliases | `opus`/`fable` → `qwen-max`, `sonnet` → `qwen-plus`, `haiku` → `qwen-flash`; `inherit` unchanged |
| `qwen-extension.json` | generated per plugin from `.claude-plugin/plugin.json` |
| `QWEN.md` | generated per plugin — component index + install instructions |
| Agent names | kept **flat** (`security-auditor`), not upstream's namespaced form (`security-compliance-security-auditor`) |
| Harness dirs | `.codex-plugin/`, `.cursor-plugin/`, `.cursor/`, `.agents/` are removed |
| `tools/` | this fork's own scripts (`convert-to-qwen.py`, `install-qwen-extensions.py`) replace upstream's adapters |
| `Makefile` | upstream's multi-harness targets do not apply; not carried over |

**Nothing about agent prompts, skill knowledge, or command workflows is rewritten.** The adaptation is structural only.

## Syncing from upstream

The adaptation is reproducible: this repo equals an upstream commit plus `tools/convert-to-qwen.py`. To re-sync:

1. Fetch the upstream commit you want and extract its tree.
2. Replace `plugins/` with upstream's.
3. Drop the harness-specific dirs listed above.
4. Run `python tools/convert-to-qwen.py` to regenerate `qwen-extension.json`, `QWEN.md`, and the model aliases.
5. Refresh `.claude-plugin/marketplace.json` from upstream.
6. Re-apply the README/QWEN-SETUP count edits and this file.

Two known gotchas when re-syncing:

- **`fable`** is Claude's top tier (above `opus`). Upstream introduced it after this fork was cut; map it to `qwen-max`. `convert-to-qwen.py` does not know it and will pass it through verbatim.
- **`qwen-extension.json` has no `hooks` key.** Qwen configures hooks in `settings.json` and extensions cannot declare them, so `hooks/` directories are carried as content but must not be advertised in the manifest.

## Working in this repo

- Plugins live under `plugins/<name>/` with `.claude-plugin/plugin.json`, `agents/`, `commands/`, `skills/`.
- Plugin names: lowercase, hyphen-separated.
- Agent frontmatter: `name`, `description`, `model`, optional `tools`, optional `color`.
- Never commit secrets. Never run destructive git (force-push, `reset --hard`, `branch -D`) without an explicit ask.

## Layout

```
qwen-code-agents/
├── .claude-plugin/marketplace.json   # Registry of all plugins
├── plugins/<name>/
│   ├── .claude-plugin/plugin.json    # Upstream source manifest
│   ├── qwen-extension.json           # Generated for Qwen Code
│   ├── QWEN.md                       # Generated per-plugin context
│   ├── agents/*.md
│   ├── commands/*.md
│   └── skills/<skill-name>/SKILL.md
├── docs/                             # Documentation
└── tools/                            # convert-to-qwen.py, install-qwen-extensions.py
```
