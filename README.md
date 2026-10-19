# Vibe Guardrails — Free Sample

Three tested guardrail rules for vibe coders using AI coding tools: Cursor, Claude Code, Codex and other AGENTS.md agents, Lovable, Bolt, and Replit.

## The 3 rules

| # | Name | Type | What it does |
|---|---|---|---|
| 01 | Secrets & Environment Variables | Rule | Never hardcode or expose API keys, tokens or passwords; keep secrets server-side. |
| 02 | Supabase Row Level Security | Rule | Every Supabase table has RLS enabled with explicit per-user policies; no service_role in the client. |
| 09 | Scope Guard: Don't Delete My Code | Rule | Change only what was asked; never remove working code, features or files silently. |

Each rule ships in four formats: Cursor (`.mdc`), Claude Code, AGENTS.md, and a paste-in prompt.

## Install

- **Cursor:** copy the `cursor/.cursor` folder into your project root. Files land in `.cursor/rules/*.mdc`. "Always" rules apply to every request; the others attach automatically by file type or when relevant.
- **Claude Code:** copy `claude-code/CLAUDE.md` (all rules combined) to your project root, or merge it into your existing one. Individual `*.CLAUDE.md` files are there if you only want some.
- **Codex / Jules / Copilot agent / other agents:** copy `agents-md/AGENTS.md` to your project root.
- **Lovable / Bolt / v0 / Replit / ChatGPT:** open `paste-in/` and paste the text into the chat (or the project's custom knowledge/instructions box). Rules ask the AI to follow them for the session.

## Tips

- Rules are plain text: edit them to match your stack.
- Rules make AI output safer; they don't replace reviewing what you ship.

## Want the full pack?

This repository is a free sample of three rules, licensed under the MIT License. The rest of Vibe Guardrails is sold separately:

- [vibeguardrails.com](https://vibeguardrails.com)
- [Ship-Safe Pack](https://williambastian.gumroad.com/l/kwljs) — $19
- [Pro Kit](https://williambastian.gumroad.com/l/wjagfl) — $39

Not affiliated with Cursor, Anthropic, Lovable, StackBlitz, Replit, Vercel or Supabase.
