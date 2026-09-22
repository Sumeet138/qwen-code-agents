# Qwen Code Agents: AI-Powered Orchestration and Automation

> **Adapted for Qwen Code** — 92 plugins, 202 agents, 183 skills, and 105 commands now working with Qwen 3.6

A comprehensive production-ready system combining **202 specialized AI agents**, **16 multi-agent workflow orchestrators**, **183 agent skills**, and **105 commands** organized into **92 focused, single-purpose plugins** — adapted for [Qwen Code](https://qwenlm.github.io/qwen-code-docs/en/).

## Credits & Attribution

> **This project is a fork/adaptation of [claude-code-workflows](https://github.com/wshobson/agents) by [Seth Hobson](https://github.com/wshobson) ([@wshobson](https://github.com/wshobson)).**
>
> All original plugin content, agent expertise, skill knowledge, command workflows, and architectural design are the work of Seth Hobson and contributors. This adaptation converts the plugin infrastructure to work with Qwen Code instead of Claude Code, while preserving 100% of the original content and intelligence.
>
> Original repository: [github.com/wshobson/agents](https://github.com/wshobson/agents)
> Original license: MIT

---

## Why This Exists

Claude Code is expensive. Qwen Code is free (OAuth: 60 req/min, 1000/day) or very cheap (API key). This project brings the same powerful agent orchestration system to Qwen Code so you can use 202 specialized AI agents **without paying for Claude**.

### Before vs After

| Aspect | Before (Claude Code) | After (Qwen Code) |
|--------|---------------------|-------------------|
| **Cost** | $3+ per 1M tokens (Sonnet) | Free (OAuth) or ~$0.02/1M tokens |
| **Model for critical tasks** | Claude Opus 4.6 | Qwen-Max |
| **Model for complex tasks** | Claude Sonnet 4.6 | Qwen-Plus |
| **Model for fast tasks** | Claude Haiku 4.5 | Qwen-Flash |
| **Plugins** | 92 | 92 (same) |
| **Agents** | 202 | 202 (same expertise) |
| **Skills** | 183 | 183 (same knowledge) |
| **Commands** | 105 | 105 (same workflows) |
| **Agent knowledge** | Identical | Identical |
| **Skill content** | Identical | Identical |
| **Workflow automation** | Identical | Identical |
| **Monthly savings** | Baseline | **~99% cheaper** |

### What Changed vs What Stayed

| Component | Changed? | Details |
|-----------|----------|---------|
| Agent system prompts | No | All 202 agents have identical expertise |
| Skill knowledge packages | No | All 183 skills with progressive disclosure |
| Command workflows | No | All 96 workflow automations |
| Plugin structure | No | Same directory organization |
| `model: opus` references | Yes | Mapped to `model: qwen-max` |
| `model: sonnet` references | Yes | Mapped to `model: qwen-plus` |
| `model: haiku` references | Yes | Mapped to `model: qwen-flash` |
| Plugin manifest | Yes | `plugin.json` + `qwen-extension.json` |
| Context files | Added | `QWEN.md` per plugin |

## Overview

This unified repository provides everything needed for intelligent automation and multi-agent orchestration across modern software development:

- **77 Focused Plugins** - Granular, single-purpose plugins optimized for minimal token usage and composability
- **202 Specialized Agents** - Domain experts with deep knowledge across architecture, languages, infrastructure, quality, data/AI, documentation, business operations, and SEO
- **183 Agent Skills** - Modular knowledge packages with progressive disclosure for specialized expertise
- **16 Workflow Orchestrators** - Multi-agent coordination systems for complex operations like full-stack development, security hardening, ML pipelines, and incident response
- **96 Commands** - Optimized utilities including project scaffolding, security scanning, test automation, and infrastructure setup

### Key Features

- **Granular Plugin Architecture**: 77 focused plugins optimized for minimal token usage
- **Comprehensive Tooling**: 105 commands including test generation, scaffolding, and security scanning
- **100% Agent Coverage**: All plugins include specialized agents
- **Agent Skills**: 183 specialized skills following for progressive disclosure and token efficiency
- **Clear Organization**: 24 categories with 1-10 plugins each for easy discovery
- **Efficient Design**: Average 3.6 components per plugin (follows Anthropic's 2-8 pattern)

### How It Works

Each plugin is completely isolated with its own agents, commands, and skills:

- **Install only what you need** - Each plugin loads only its specific agents, commands, and skills
- **Minimal token usage** - No unnecessary resources loaded into context
- **Mix and match** - Compose multiple plugins for complex workflows
- **Clear boundaries** - Each plugin has a single, focused purpose
- **Progressive disclosure** - Skills load knowledge only when activated

**Example**: Installing `python-development` loads 3 Python agents, 1 scaffolding tool, and makes 16 skills available (~1000 tokens), not the entire marketplace.

## Quick Start

### Step 1: Install Qwen Code

```bash
npm install -g @anthropic-ai/qwen-code
qwen --version
```

### Step 2: Authenticate (Free)

```bash
# Free tier: 60 requests/min, 1,000 requests/day
qwen auth qwen-oauth

# Or use API key for higher limits
qwen auth api-key
```

### Step 3: Clone This Repo

```bash
git clone https://github.com/SumeetGond/qwen-code-agents.git
cd qwen-code-agents
```

### Step 4: Install Extensions

```bash
# Install ALL 92 plugins as Qwen Code extensions
python tools/install-qwen-extensions.py

# Or install specific plugins only
python tools/install-qwen-extensions.py --plugins python-development backend-development conductor

# View available plugins
python tools/install-qwen-extensions.py --list
```

### Step 5: Start Using

```bash
qwen
```

```bash
# Try a command
/conductor:setup

# Use an agent
"Use python-pro to write async API code"

# View skills
/skills

# Manage agents
/agents manage
```

### Plugins & What They Bundle

| Plugin | Agents | Skills |
|--------|--------|--------|
| `python-development` | python-pro, django-pro, fastapi-pro | 16 skills |
| `javascript-typescript` | typescript-pro | 4 skills |
| `backend-development` | backend-architect, graphql-specialist | 3 skills |
| `conductor` | conductor-validator | 3 skills |
| `full-stack-orchestration` | 7 specialized agents | orchestration |
| `security-scanning` | security-auditor | 8 skills |

### Troubleshooting

**Commands not found** → Restart Qwen Code after installing extensions.

**Extensions not appearing** → Check they're in the correct directory:
- **Windows**: `%USERPROFILE%\.qwen\extensions\`
- **macOS/Linux**: `~/.qwen/extensions/`

**Rate limit errors** → Switch from OAuth to API key:
```bash
qwen auth api-key
```

## Documentation

### Core Guides

- **[Plugin Reference](docs/plugins.md)** - Complete catalog of all 92 plugins
- **[Agent Reference](docs/agents.md)** - All 202 agents organized by category
- **[Agent Skills](docs/agent-skills.md)** - 183 specialized skills with progressive disclosure
- **[Usage Guide](docs/usage.md)** - Commands, workflows, and best practices
- **[Architecture](docs/architecture.md)** - Design principles and patterns
- **[PluginEval](docs/plugin-eval.md)** - Quality evaluation framework (layers, dimensions, scoring)

### Quick Links

- [Installation](#quick-start) - Get started in 2 steps
- [Essential Plugins](docs/plugins.md#quick-start---essential-plugins) - Top plugins for immediate productivity
- [Command Reference](docs/usage.md#command-reference-by-category) - All slash commands organized by category
- [Multi-Agent Workflows](docs/usage.md#multi-agent-workflow-examples) - Pre-configured orchestration examples
- [Model Configuration](docs/agents.md#model-configuration) - Haiku/Sonnet hybrid orchestration

## What's New

### PluginEval — Quality Evaluation Framework (NEW)

A three-layer evaluation framework for measuring and certifying plugin/skill quality:

```bash
/plugin install plugin-eval@claude-code-workflows
```

- **Three Evaluation Layers** — Static analysis (instant), LLM judge (semantic), Monte Carlo simulation (statistical)
- **10 Quality Dimensions** — Triggering accuracy, orchestration fitness, output quality, scope calibration, progressive disclosure, token efficiency, robustness, structural completeness, code template quality, ecosystem coherence
- **Quality Badges** — Platinum (★★★★★), Gold (★★★★), Silver (★★★), Bronze (★★)
- **Anti-Pattern Detection** — OVER_CONSTRAINED, EMPTY_DESCRIPTION, MISSING_TRIGGER, BLOATED_SKILL, ORPHAN_REFERENCE, DEAD_CROSS_REF
- **Statistical Rigor** — Wilson score CI, bootstrap CI, Clopper-Pearson exact CI, Elo ranking
- **CLI + Claude Code** — `uv run plugin-eval score/certify/compare` or `/eval`, `/certify`, `/compare` commands
- **CI Gate** — `--threshold` flag exits non-zero below a minimum score

```bash
# Quick evaluation (static only, instant)
uv run plugin-eval score path/to/skill --depth quick

# Standard evaluation (static + LLM judge)
uv run plugin-eval score path/to/skill --depth standard

# Full certification (all layers + Elo)
uv run plugin-eval certify path/to/skill
```

[→ View PluginEval documentation](docs/plugin-eval.md)

### Agent Teams Plugin

Orchestrate multi-agent teams for parallel workflows using Claude Code's experimental Agent Teams feature:

```bash
/plugin install agent-teams@claude-code-workflows
```

- **7 Team Presets** — `review`, `debug`, `feature`, `fullstack`, `research`, `security`, `migration`
- **Parallel Code Review** — `/team-review src/ --reviewers security,performance,architecture`
- **Hypothesis-Driven Debugging** — `/team-debug "API returns 500" --hypotheses 3`
- **Parallel Feature Development** — `/team-feature "Add OAuth2 auth" --plan-first`
- **Research Teams** — Parallel investigation across codebase and web sources
- **Security Audits** — 4 reviewers covering OWASP, auth, dependencies, and secrets
- **Migration Support** — Coordinated migration with parallel streams and correctness verification

Includes 4 specialized agents, 7 commands, and 6 skills with reference documentation.

[→ View agent-teams documentation](plugins/agent-teams/README.md)

### Conductor Plugin — Context-Driven Development

Transforms Claude Code into a project management tool with a structured **Context → Spec & Plan → Implement** workflow:

```bash
/plugin install conductor@claude-code-workflows
```

- **Interactive Setup** — `/conductor:setup` creates product vision, tech stack, workflow rules, and style guides
- **Track-Based Development** — `/conductor:new-track` generates specifications and phased implementation plans
- **TDD Workflow** — `/conductor:implement` executes tasks with verification checkpoints
- **Semantic Revert** — `/conductor:revert` undoes work by logical unit (track, phase, or task)
- **State Persistence** — Resume setup across sessions with persistent project context
- **3 Skills** — Context-driven development, track management, workflow patterns

[→ View Conductor documentation](plugins/conductor/README.md)

### Agent Skills (183 skills across 92 plugins)

Specialized knowledge packages following Anthropic's progressive disclosure architecture:

**Language Development:**

- **Python** (5 skills): async patterns, testing, packaging, performance, UV package manager
- **JavaScript/TypeScript** (4 skills): advanced types, Node.js patterns, testing, modern ES6+

**Infrastructure & DevOps:**

- **Kubernetes** (4 skills): manifests, Helm charts, GitOps, security policies
- **Cloud Infrastructure** (4 skills): Terraform, multi-cloud, hybrid networking, cost optimization
- **CI/CD** (4 skills): pipeline design, GitHub Actions, GitLab CI, secrets management

**Development & Architecture:**

- **Backend** (3 skills): API design, architecture patterns, microservices
- **LLM Applications** (8 skills): LangGraph, prompt engineering, RAG, evaluation, embeddings, similarity search, vector tuning, hybrid search

**Blockchain & Web3** (4 skills): DeFi protocols, NFT standards, Solidity security, Web3 testing

**Project Management:**

- **Conductor** (3 skills): context-driven development, track management, workflow patterns

**And more:** Framework migration, observability, payment processing, ML operations, security scanning

[→ View complete skills documentation](docs/agent-skills.md)

### Three-Tier Model Strategy

Strategic model assignment for optimal performance and cost:

| Tier | Claude Model | Qwen Model | Agents | Use Case |
|------|-------------|------------|--------|----------|
| **Tier 1** | Opus 4.6 / Fable 5 | **Qwen-Max** | 56 | Critical architecture, security, code review, production coding |
| **Tier 2** | Inherit | **Inherit** | 52 | Complex tasks - uses your session's default model |
| **Tier 3** | Sonnet 4.6 | **Qwen-Plus** | 70 | Docs, testing, debugging, API design, DX optimization |
| **Tier 4** | Haiku 4.5 | **Qwen-Flash** | 24 | Fast operational tasks (SEO, deployment, content) |

**Tier 2 Flexibility (`inherit`):**
Agents marked `inherit` use your session's default model, letting you balance cost and capability.

**Cost Comparison (per 1M tokens):**

| Tier | Claude Cost | Qwen Cost | Savings |
|------|-----------|-----------|---------|
| Tier 1 (Max) | $5/$25 (input/output) | ~$0.04 | ~99% |
| Tier 3 (Plus) | $3/$15 | ~$0.02 | ~99% |
| Tier 4 (Flash) | $1/$5 | ~$0.01 | ~99% |
| **Free (OAuth)** | N/A | **$0** | **100%** |

Orchestration patterns combine models for efficiency:

```
Qwen-Max (architecture) → Qwen-Plus (development) → Qwen-Flash (deployment)
```

## Popular Use Cases

### Full-Stack Feature Development

```bash
/full-stack-orchestration:full-stack-feature "user authentication with OAuth2"
```

Coordinates 7+ agents: backend-architect → database-architect → frontend-developer → test-automator → security-auditor → deployment-engineer → observability-engineer

[→ View all workflow examples](docs/usage.md#multi-agent-workflow-examples)

### Security Hardening

```bash
/security-scanning:security-hardening --level comprehensive
```

Multi-agent security assessment with SAST, dependency scanning, and code review.

### Python Development with Modern Tools

```bash
/python-development:python-scaffold fastapi-microservice
```

Creates production-ready FastAPI project with async patterns, activating skills:

- `async-python-patterns` - AsyncIO and concurrency
- `python-testing-patterns` - pytest and fixtures
- `uv-package-manager` - Fast dependency management

### Kubernetes Deployment

```bash
# Activates k8s skills automatically
"Create production Kubernetes deployment with Helm chart and GitOps"
```

Uses kubernetes-architect agent with 4 specialized skills for production-grade configs.

[→ View complete usage guide](docs/usage.md)

## Plugin Categories

**25 categories, 92 plugins:**

- 🎨 **Development** (6) - debugging, backend, frontend, multi-platform
- 📚 **Documentation** (5) - code docs, API specs, diagrams, C4 architecture, **HADS** (Human-AI Document Standard)
- 🔄 **Workflows** (8) - git, full-stack, TDD, **Conductor** (context-driven development), **Agent Teams** (multi-agent orchestration)
- ✅ **Testing** (1) - unit testing
- 🔍 **Quality** (4) - comprehensive review, performance
- 🛠️ **Utilities** (5) - general-purpose helpers, **skill-forge-essentials**
- 🤖 **AI & ML** (6) - LLM apps, agent orchestration, context, MLOps, **LLM fine-tuning**
- 🧠 **Memory** (1, external) - **pensyve** (persistent memory)
- 📊 **Data** (2) - data engineering, data validation
- 🗄️ **Database** (2) - database design, migrations
- 🚨 **Operations** (4) - incident response, diagnostics, distributed debugging, observability
- ⚡ **Performance** (2) - application performance, database/cloud optimization
- ☁️ **Infrastructure** (5) - deployment, validation, Kubernetes, cloud, CI/CD
- 🔒 **Security** (7) - scanning, compliance, backend/API, frontend/mobile, **block-no-verify** (git hook bypass guard)
- 🛡️ **Governance** (3) - **protect-mcp** (Cedar + signed receipts), **review-agent-governance**, **signed-audit-trails**
- 🔄 **Modernization** (2) - legacy migration and refactoring
- 🌐 **API** (2) - API tooling
- 📢 **Marketing** (5) - SEO content, technical SEO, SEO analysis, content marketing, **social-publishing**
- 💼 **Business** (5) - analytics, HR/legal, customer/sales, **operating-kit**
- 💻 **Languages** (10) - Python, JS/TS, systems, JVM, scripting, functional, embedded
- 🔗 **Blockchain** (1) - smart contracts, DeFi, Web3
- 💰 **Finance** (1) - quantitative trading, risk management
- 💳 **Payments** (1) - Stripe, PayPal, billing
- 🎮 **Gaming** (1) - Unity, Minecraft plugins
- ♿ **Accessibility** (1) - WCAG and a11y
- 🎨 **Creative** (3) - creative tooling, **brand-landingpage**, **pptx-deck-creation**

[→ View complete plugin catalog](docs/plugins.md)

## Architecture Highlights

### Granular Design

- **Single responsibility** - Each plugin does one thing well
- **Minimal token usage** - Average 3.6 components per plugin
- **Composable** - Mix and match for complex workflows
- **100% coverage** - All 202 agents accessible across plugins

### Progressive Disclosure (Skills)

Three-tier architecture for token efficiency:

1. **Metadata** - Name and activation criteria (always loaded)
2. **Instructions** - Core guidance (loaded when activated)
3. **Resources** - Examples and templates (loaded on demand)

### Repository Structure

```
qwen-code-agents/
├── .claude-plugin/
│   └── marketplace.json          # Original Claude marketplace (preserved)
├── plugins/
│   ├── python-development/
│   │   ├── qwen-extension.json   # Qwen Code extension manifest
│   │   ├── QWEN.md              # Qwen context file
│   │   ├── .claude-plugin/       # Original Claude plugin (preserved)
│   │   ├── agents/               # 3 Python experts (model: qwen-max)
│   │   ├── commands/             # Scaffolding tool
│   │   └── skills/               # 16 specialized skills
│   ├── conductor/
│   │   ├── qwen-extension.json
│   │   ├── agents/               # Conductor validator
│   │   ├── commands/             # setup, implement, status, revert...
│   │   └── skills/               # 3 workflow skills
│   └── ... (74 more plugins)
├── tools/
│   ├── convert-to-qwen.py       # Conversion script
│   └── install-qwen-extensions.py # Install/uninstall extensions
├── docs/                          # Comprehensive documentation
├── QWEN-SETUP.md                  # Detailed Qwen Code setup guide
└── README.md                      # This file
```

[→ View architecture details](docs/architecture.md)

## Tools

### convert-to-qwen.py

Converts Claude plugins to Qwen Code extensions:

```bash
python tools/convert-to-qwen.py              # Full conversion
python tools/convert-to-qwen.py --dry-run    # Preview only
python tools/convert-to-qwen.py --restore    # Revert to Claude model names
```

### install-qwen-extensions.py

Installs extensions into Qwen Code's directory:

```bash
python tools/install-qwen-extensions.py                # Install all
python tools/install-qwen-extensions.py --list         # List available
python tools/install-qwen-extensions.py --plugins X Y  # Install specific
python tools/install-qwen-extensions.py --uninstall    # Remove all
```

## Contributing

To add new agents, skills, or commands:

1. Create or edit files in the appropriate plugin directory under `plugins/`
2. Run `python tools/convert-to-qwen.py` to regenerate Qwen extension files
3. Run `python tools/install-qwen-extensions.py` to reinstall
4. Restart Qwen Code to pick up changes

## Resources

### Qwen Code Documentation

- [Qwen Code Docs](https://qwenlm.github.io/qwen-code-docs/en/)
- [Qwen Code Extensions](https://qwenlm.github.io/qwen-code-docs/en/users/extension/introduction/)
- [Qwen Code Skills](https://qwenlm.github.io/qwen-code-docs/en/users/features/skills/)
- [Qwen Code Subagents](https://qwenlm.github.io/qwen-code-docs/en/users/features/sub-agents/)
- [Qwen API Reference](https://www.alibabacloud.com/help/en/model-studio/qwen-api-reference/)

### Original Project

- [Original Repository (wshobson/agents)](https://github.com/wshobson/agents)
- [Plugin Reference](docs/plugins.md)
- [Agent Reference](docs/agents.md)
- [Agent Skills Guide](docs/agent-skills.md)
- [Usage Guide](docs/usage.md)
- [Architecture](docs/architecture.md)

## License

MIT License - see [LICENSE](LICENSE) file for details.

Original work by [Seth Hobson](https://github.com/wshobson). Qwen Code adaptation by [Sumeet Gond](https://github.com/SumeetGond).
