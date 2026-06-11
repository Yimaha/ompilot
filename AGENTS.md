# ompilot — Contributor Instructions

Rules for any AI agent working in this repo. These are hard constraints.

## 1. All Changes Are Public

Every commit, file, comment, and message pushed to this repo is visible to the world. Do not include:
- API keys, tokens, passwords, or credentials of any kind
- Internal URLs, hostnames, or IP addresses from private infrastructure
- Personal information (names, emails, phone numbers) unless explicitly intended to be public
- Negative or disparaging remarks about any person, project, or organization
- Placeholder or example data that could be mistaken for real secrets

## 2. Cross-Platform Mobile Compatibility

The phone client is a PWA that must work on both iOS Safari and Android Chrome. Prefer Web APIs with broad support across both platforms. Avoid Chrome-only APIs unless a documented iOS fallback exists.

## 3. Cross-Platform Desktop Compatibility

The bridge server must run on macOS and Linux. Prefer Bun's built-in APIs over OS-specific shell commands. Bind to `127.0.0.1` or the Tailscale interface, never `0.0.0.0`.

## 4. OMP Protocol Stability

OMP's RPC and ACP protocols may add new commands but existing ones are backward-compatible. Parse only the fields you need. Ignore unknown fields. Never hardcode the OMP version.

## 5. Repo Boundaries

- This is the **public code repo**. Code, README, and contributor-facing docs live here.
- Internal planning and specs live in a separate private companion repo. Do not commit planning documents here.
- Do not reference private repos or internal URLs in code comments or commit messages.
- The companion repo is discovered automatically via the cross-agent rule in `~/.agent/AGENTS.md`. If you are an AI agent and not seeing the specs, ensure that file is loaded in your context.
