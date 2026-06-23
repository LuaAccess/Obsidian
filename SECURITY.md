# Security Policy

## Scope

This repository contains Claude Skill definitions (`.md` instruction files) and plugin manifests (`.json`).
There is no executable code in this repo. Security considerations are:

1. **Prompt injection** — Skill content must not contain instructions that hijack Claude's behaviour
2. **`eval` usage** — The `obsidian-cli` skill documents `obsidian eval`, which runs arbitrary JS in Obsidian
3. **Supply chain** — Plugin manifests must reflect the correct owner/repository

## Using `obsidian eval` Safely

The `obsidian eval code="..."` command documented in `skills/obsidian-cli/SKILL.md` executes JavaScript
inside the Obsidian app context with full vault access.

**Rules:**
- Only use `eval` in development vaults, never production
- Never pass user-supplied strings directly to `obsidian eval`
- Review any `eval` code before running it

## Reporting Issues

If you find prompt injection, misleading trigger descriptions, or other skill integrity issues,
open a GitHub issue or email the repo owner directly.

## Supported Versions

| Version | Supported |
|---------|-----------|
| 1.0.1   | ✅ Yes    |
| < 1.0.0 | ❌ No     |
