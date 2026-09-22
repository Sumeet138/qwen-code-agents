# protect-mcp

Cedar policy enforcement + Ed25519 signed receipts for every Claude Code tool call. First cryptographic governance plugin — receipts independently verifiable offline.

## Components

### Agents

- **policy-enforcer**: See `agents/policy-enforcer.md`
- **receipt-verifier**: See `agents/receipt-verifier.md`

### Commands

- **/protect-mcp:audit-chain**: See `commands/audit-chain.md`
- **/protect-mcp:verify-receipt**: See `commands/verify-receipt.md`

### Skills

- **protect-mcp-setup**: See `skills/protect-mcp-setup/SKILL.md`

## Usage

This extension is designed for Qwen Code. Install it with:

```
qwen extensions install <path-to-this-directory>
```

Or copy to `~/.qwen/extensions/` for global availability.
