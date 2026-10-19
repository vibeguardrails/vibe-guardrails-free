# Secrets & Environment Variables

> Never hardcode or expose API keys, tokens or passwords; keep secrets server-side.

## Rules
- Never write a real API key, token, password or connection string into source code, comments, tests, docs or commit messages. Use `process.env.NAME` (or the framework equivalent) and add `NAME=` with an empty value to `.env.example`.
- Before creating or editing any file, confirm `.env`, `.env.local` and `.env.*.local` are listed in `.gitignore`. If they are not, add them first.
- Only variables meant to be public may use client-exposed prefixes (`NEXT_PUBLIC_`, `VITE_`, `EXPO_PUBLIC_`, `PUBLIC_`). Secret keys (Stripe secret key, Supabase service_role key, OpenAI/Anthropic keys, database URLs, webhook secrets) must never use these prefixes and must never be imported into client components.
- Calls that need a secret key go through a server route, server action, or edge function. The browser calls that endpoint, never the third-party API directly.
- Validate required env vars at startup (e.g. a `env.ts` that throws a clear error listing missing names) instead of failing deep inside a request.
- Never log full secrets. If you must log a key for debugging, log only the last 4 characters.
- If you find a secret already committed, stop and tell the user: it must be rotated at the provider, not just deleted from the file, because it remains in git history.

## Check before you finish
- [ ] `grep -rE "(sk_live|sk_test|service_role|-----BEGIN|AKIA[0-9A-Z]{16})"` over the changed files returns nothing.
- [ ] No secret variable is referenced from a file that runs in the browser.
