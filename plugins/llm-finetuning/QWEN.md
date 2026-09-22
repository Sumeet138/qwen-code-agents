# llm-finetuning

Eval-gated LLM fine-tuning lifecycle: LoRA/QLoRA SFT, preference optimization (DPO/ORPO/KTO), GRPO/RLVR, vision SFT, and quantized export — Unsloth-first with TRL fallback, no eval harness means no fine-tune

## Components

### Agents

- **llm-finetuning-architect**: See `agents/llm-finetuning-architect.md`
- **llm-finetuning-eval-engineer**: See `agents/llm-finetuning-eval-engineer.md`
- **llm-finetuning-training-engineer**: See `agents/llm-finetuning-training-engineer.md`

### Commands

- **/llm-finetuning:finetune**: See `commands/finetune.md`
- **/llm-finetuning:promote-checkpoint**: See `commands/promote-checkpoint.md`

### Skills

- **checkpoint-promotion**: See `skills/checkpoint-promotion/SKILL.md`
- **dataset-curation**: See `skills/dataset-curation/SKILL.md`
- **eval-harness-first**: See `skills/eval-harness-first/SKILL.md`
- **finetuning-method-selection**: See `skills/finetuning-method-selection/SKILL.md`
- **grpo-rlvr-training**: See `skills/grpo-rlvr-training/SKILL.md`
- **lora-qlora-recipes**: See `skills/lora-qlora-recipes/SKILL.md`
- **preference-optimization**: See `skills/preference-optimization/SKILL.md`
- **quantized-export**: See `skills/quantized-export/SKILL.md`
- **trace-to-training-data**: See `skills/trace-to-training-data/SKILL.md`
- **vision-sft**: See `skills/vision-sft/SKILL.md`

## Usage

This extension is designed for Qwen Code. Install it with:

```
qwen extensions install <path-to-this-directory>
```

Or copy to `~/.qwen/extensions/` for global availability.
