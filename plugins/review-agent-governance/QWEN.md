# review-agent-governance

Require a human approval signal before an AI agent can post PR reviews, comments, merges, or writes to CI config. Cedar-gated, receipt-signed, designed for the Hermes-style failure mode where a review bot posts without oversight.

## Components

### Agents

- **review-policy-author**: See `agents/review-policy-author.md`

### Commands

- **/review-agent-governance:approve-review**: See `commands/approve-review.md`
- **/review-agent-governance:list-pending**: See `commands/list-pending.md`

### Skills

- **review-agent-setup**: See `skills/review-agent-setup/SKILL.md`

## Usage

This extension is designed for Qwen Code. Install it with:

```
qwen extensions install <path-to-this-directory>
```

Or copy to `~/.qwen/extensions/` for global availability.
