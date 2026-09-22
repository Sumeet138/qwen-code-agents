# operating-kit

Portable operating method: session lifecycle agents (session-start/end), pre-ship code review, deploy with live verification, and production log health check. All agents use {{placeholders}} that adapt to your project.

## Components

### Agents

- **code-review-preshipment**: See `agents/code-review-preshipment.md`
- **deploy-with-verification**: See `agents/deploy-with-verification.md`
- **prod-logs-health-check**: See `agents/prod-logs-health-check.md`
- **session-end**: See `agents/session-end.md`
- **session-start**: See `agents/session-start.md`

## Usage

This extension is designed for Qwen Code. Install it with:

```
qwen extensions install <path-to-this-directory>
```

Or copy to `~/.qwen/extensions/` for global availability.
