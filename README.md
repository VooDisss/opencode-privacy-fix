# OpenCode Network Guide

An informational guide to [OpenCode](https://github.com/anomalyco/opencode)'s outbound network connections — what the CLI binary contacts, when, and how to control it.

OpenCode is an excellent open-source agentic coding tool. This is not a security alert.

> **Corrections (March 25, 2026):** An earlier version of this page incorrectly claimed OpenCode had no privacy policy (it does — [see here](https://opencode.ai/legal/privacy-policy)), that PostHog and Honeycomb were in the CLI binary (they're not), and framed opt-in features as undisclosed concerns. Apologies to the OpenCode team.

**Full guide:** [VooDisss.github.io/opencode-privacy-fix](https://VooDisss.github.io/opencode-privacy-fix/)

## What the CLI binary contacts

| Domain | When it fires | Opt-in? | Disable flag |
|--------|--------------|---------|-------------|
| `app.opencode.ai` | Web UI page loads (not TUI) | Web UI is experimental | Not yet (devs plan to bundle) |
| `api.opencode.ai` | `opencode github` command | **Yes** | No |
| `opencode.ai` | Auto-update check | No | **Yes** — `OPENCODE_DISABLE_AUTOUPDATE` |
| `opncd.ai` | Session sharing | **Yes** — must explicitly share | **Yes** — `OPENCODE_DISABLE_SHARE` |
| `models.dev` | Startup (only if cache fails) | No | **Yes** — `OPENCODE_DISABLE_MODELS_FETCH` |

Your prompts are NOT sent through the web UI proxy — that only handles HTML/JS/CSS.

## Links

- [OpenCode Privacy Policy](https://opencode.ai/legal/privacy-policy)
- [OpenCode CLI Docs](https://opencode.ai/docs/cli)
- [OpenCode Share Docs](https://opencode.ai/docs/share)
