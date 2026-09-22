# plugin-eval

Three-layer quality evaluation framework for Claude Code plugins with Elo ranking

## Components

### Agents

- **eval-judge**: See `agents/eval-judge.md`
- **eval-orchestrator**: See `agents/eval-orchestrator.md`

### Commands

- **/plugin-eval:certify**: See `commands/certify.md`
- **/plugin-eval:compare**: See `commands/compare.md`
- **/plugin-eval:eval**: See `commands/eval.md`

### Skills

- **evaluation-methodology**: See `skills/evaluation-methodology/SKILL.md`

## Usage

This extension is designed for Qwen Code. Install it with:

```
qwen extensions install <path-to-this-directory>
```

Or copy to `~/.qwen/extensions/` for global availability.
