# Architecture

Top-level architectural map for **qwen-code-agents**, the Qwen Code adaptation of the [claude-agents marketplace](https://github.com/wshobson/agents). Detail for the upstream content itself lives in [`docs/architecture.md`](docs/architecture.md).

## Invariants

1. **Upstream is the source of truth for content.** Agent / skill / command bodies under `plugins/<name>/` originate upstream and are carried through unmodified in substance. This fork adds structure, never rewrites expertise.

2. **The adaptation is mechanical and reproducible.** This repo equals an upstream commit plus `tools/convert-to-qwen.py`. That script rewrites `model:` aliases, emits `qwen-extension.json` per plugin, and generates each `QWEN.md`. Nothing else is transformed, so a re-sync is a script run plus conflict review — not a hand-merge.

3. **Two context files, one audience each.** `AGENTS.md` (this repo's) describes the *fork* and the sync procedure. `CLAUDE.md` is upstream's contributor-facing project context, carried verbatim to keep upstream diffs legible. `QWEN.md` files are generated per plugin.

4. **Structural adaptation only.** Agent names stay flat (`security-auditor`), not upstream's namespaced form (`security-compliance-security-auditor`), because Qwen already namespaces agents as `plugin:agent`. Harness dirs upstream needs — `.codex-plugin/`, `.cursor-plugin/`, `.cursor/`, `.agents/` — are stripped.

5. **Progressive disclosure all the way down.** Skill bodies stay lean and offload detail to `references/`. `QWEN.md` files are component indexes, not documentation dumps.

## Component overview

```
qwen-code-agents/
├── AGENTS.md                       # This fork's context file (fork + sync procedure)
├── CLAUDE.md                       # Upstream's project context (carried verbatim)
├── ARCHITECTURE.md                 # This file
├── README.md                       # User-facing landing page
├── QWEN-SETUP.md                   # Step-by-step Qwen Code setup
├── CONTRIBUTING.md                 # Upstream contribution guide
├── .claude-plugin/marketplace.json # Plugin registry (94 entries)
├── plugins/<name>/
│   ├── .claude-plugin/plugin.json  # Upstream manifest — upstream's source of truth
│   ├── qwen-extension.json         # GENERATED — Qwen Code manifest
│   ├── QWEN.md                     # GENERATED — per-plugin component index
│   ├── agents/*.md                 # model: aliased to qwen-* tiers
│   ├── commands/*.md               # unmodified
│   ├── skills/<name>/SKILL.md      # unmodified
│   └── hooks/                      # carried as content; NOT advertised in the manifest
├── docs/                           # Upstream documentation set
└── tools/
    ├── convert-to-qwen.py          # The adaptation, in full
    └── install-qwen-extensions.py  # Copies plugins into ~/.qwen/extensions/
```

## The adaptation, precisely

| Transform | Input | Output |
| --- | --- | --- |
| Model alias | `model: opus` / `model: fable` | `model: qwen-max` |
| Model alias | `model: sonnet` | `model: qwen-plus` |
| Model alias | `model: haiku` | `model: qwen-flash` |
| Model alias | `model: inherit` | `model: inherit` (unchanged) |
| Manifest | `.claude-plugin/plugin.json` | `qwen-extension.json` |
| Context | (component dirs) | `QWEN.md` |

`fable` is Claude's top tier, above `opus`. Upstream added it after this fork was cut, so `convert-to-qwen.py` predates it and will pass it through unchanged — map it to `qwen-max` when re-syncing.

## Why `hooks/` is not in the manifest

`qwen-extension.json` accepts `name`, `version`, `mcpServers`, `channels`, `contextFileName`, `commands`, `skills`, `agents`, `workflows`, and `settings`. There is **no `hooks` key** — Qwen configures hooks in `settings.json`, and extensions cannot declare them. The two plugins that ship `hooks/` upstream (`protect-mcp`, `review-agent-governance`) keep those files on disk, but the generated manifest omits the key so Qwen does not reject an unknown field.

## Quality gates

Upstream's `make validate` / `make garden` / `make smoke-test` targets depend on the adapter framework under `tools/adapters/`, which this fork does not carry, so its `Makefile` is not included. Validation here is:

- Every plugin has `.claude-plugin/plugin.json`, `qwen-extension.json`, and `QWEN.md`.
- No `model:` line carries a Claude alias (`opus`, `sonnet`, `haiku`, `fable`).
- Every `qwen-extension.json` parses and contains no `hooks` key.
- No `.codex-plugin/`, `.cursor-plugin/`, `.cursor/`, or `.agents/` directories remain under `plugins/`.

`plugins/plugin-eval/` is the one place with a real test suite and is runnable on its own via `uv`.
