# secure-my-app

A universal security audit and hardening skill for AI coding agents. When loaded, the agent audits web apps, mobile apps, and AI apps against OWASP-backed rules, interviews you about each finding with hyper-specific questions, and fixes things only after you approve.

**Works with:** opencode, Claude Code, Cursor, and any agent that can load a SKILL.md.

## Install

### opencode / skills.sh

```bash
npx skills add TurnkeyIsaiah/secure-my-app
```

### Claude Code

```bash
npx @anthropic-ai/claude-code add-skill TurnkeyIsaiah/secure-my-app
```

### Manual

Clone the repo and point your agent to `SKILL.md`:

```bash
git clone https://github.com/TurnkeyIsaiah/secure-my-app.git
```

Then configure your agent to load `path/to/secure-my-app/SKILL.md` as an instruction file.

## Usage

Once loaded, trigger the skill by saying something like:

- "Audit this app for security issues"
- "Harden my app before launch"
- "Check for vulnerabilities"
- "Make this production-ready"
- "Secure this [web/mobile/AI] app"

The agent will:

1. **Scan** your codebase against 20+ security categories
2. **Interview** you about each finding with concrete, file-specific questions (what to use, what values to set, what trade-offs to accept)
3. **Fix** things only after you approve — using your answers as the build spec

## Coverage

| Category | Checks |
|----------|--------|
| Universal | HTTPS, auth, authorization, input validation, SQL injection, API keys, secrets, env vars, DB security, Stripe, rate limiting, file uploads, XSS, cookies, dependencies |
| Web | CORS, CSP, CSRF, admin pages |
| Mobile | No secrets in binary, secure token storage (Keychain/Keystore/SecureStore), fake request protection, no sensitive logging |
| AI/LLM | Prompt injection, data leakage, tool restrictions, usage abuse |

## How it differs from a static checklist

Most security tools just dump a list of issues. This skill forces the agent to ask you **hyper-specific questions** about each finding — referencing exact files, lines, and patterns — so your answers double as build prompts for the fixes. No vague "how should I fix this?" — only concrete options tailored to your stack.

## Free Resources

The skill includes 25+ linked OWASP cheat sheets, tool docs, and free testing tools. No paid services required.

## License

MIT
