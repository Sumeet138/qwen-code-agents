# dgx-spark-ops

NVIDIA DGX Spark (GB10 Grace Blackwell) environment operations: aarch64/CUDA-13 stack setup, training gotcha preflights, and unified-memory/thermal management for local ML workloads

## Components

### Agents

- **dgx-spark-ops-engineer**: See `agents/dgx-spark-ops-engineer.md`

### Commands

- **/dgx-spark-ops:spark-preflight**: See `commands/spark-preflight.md`

### Skills

- **spark-environment-setup**: See `skills/spark-environment-setup/SKILL.md`
- **spark-memory-thermal-ops**: See `skills/spark-memory-thermal-ops/SKILL.md`
- **spark-training-gotchas**: See `skills/spark-training-gotchas/SKILL.md`

## Usage

This extension is designed for Qwen Code. Install it with:

```
qwen extensions install <path-to-this-directory>
```

Or copy to `~/.qwen/extensions/` for global availability.
