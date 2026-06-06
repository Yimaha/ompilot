# ompilot

Phone-in-pocket remote control for [Oh My Pi (OMP)](https://github.com/can1357/oh-my-pi) — you pilot your OMP from your phone, through a relay you own.

**Status:** Research + scoping. Not yet usable.

## What

Claude Code's remote control lets you send prompts from your phone to a Claude Code instance running on your laptop. OMP has the protocol surface for this (RPC mode, ACP mode) but no mobile client or relay. ompilot builds that.

```
[Phone PWA] ──WebSocket──▶ [Bridge] ──stdio──▶ [omp acp]
```

## Approach

Dedicated to OMP, not a generic multi-agent wrapper. This lets us:

- Render OMP-specific features (hashline edit previews, time-traveling stream rules, model picker, @-file completion)
- Track OMP's protocol evolution closely
- Keep the codebase small and single-purpose

## Setup (coming soon)

No release yet. The plan for v0:

1. Install Tailscale on laptop and phone
2. Run `npx ompilot` on the laptop
3. Scan the QR code with your phone
4. Start piloting OMP from anywhere

## References

- [Feature request thread](https://github.com/can1357/oh-my-pi/issues/436)
- [OMP's RPC protocol](https://github.com/can1357/oh-my-pi/blob/main/docs/rpc.md)
- [OMP's ACP protocol](https://github.com/can1357/oh-my-pi/blob/main/packages/coding-agent/src/modes/acp/)
- [Claude Code Remote Control](https://code.claude.com/docs/en/remote-control)
- [Paseo OMP provider](https://github.com/getpaseo/paseo/pull/1177)
