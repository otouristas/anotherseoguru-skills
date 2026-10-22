# AnotherSEOGuru App agent skills

SEO workflows for Claude Code, Codex, Cursor and any AI agent that reads `SKILL.md`.
Each skill gives your agent one repeatable job: find the fixes worth the most clicks, fix a task in
your code, write the weekly report, check whether AI assistants cite you, or turn a crawl into a
fix list. The data comes from your own Google Search Console through
[AnotherSEOGuru App](https://anotherseoguru.com/en/platform).

## 1. Connect the MCP server first

These skills do nothing on their own. Add the AnotherSEOGuru App MCP server and sign in once:

```
https://app.anotherseoguru.com/mcp
```

| Client | How |
| --- | --- |
| Claude Code | `claude mcp add --transport http --scope user anotherseoguru https://app.anotherseoguru.com/mcp`, then `/mcp` |
| Codex | `codex mcp add anotherseoguru --url https://app.anotherseoguru.com/mcp` and `codex mcp login anotherseoguru` |
| Claude, ChatGPT | Add the URL as a custom connector (OAuth) |
| Cursor | `~/.cursor/mcp.json`: `{ "mcpServers": { "anotherseoguru": { "url": "https://app.anotherseoguru.com/mcp" } } }` |
| Grok Bot | Send: `Connect this MCP server: https://app.anotherseoguru.com/mcp` |
| OpenClaw | `openclaw mcp add anotherseoguru --url https://app.anotherseoguru.com/mcp --transport streamable-http --auth oauth` |
| Hermes Agent | `hermes mcp add anotherseoguru --url https://app.anotherseoguru.com/mcp --auth oauth` |
| Local-only clients | command `npx`, args `["-y", "mcp-remote", "https://app.anotherseoguru.com/mcp"]` |

Full steps: <https://anotherseoguru.com/en/platform/mcp#clients>. You need an AnotherSEOGuru App
account with Search Console connected; sign-up is free at <https://app.anotherseoguru.com/signup>.

## 2. Install the skills

```sh
npx skills add otouristas/anotherseoguru-skills
```

Pick skills and agents interactively, or take them all:

```sh
npx skills add otouristas/anotherseoguru-skills --skill '*'
```

Or copy the folders under `skills/` into your agent's skills directory (for Claude Code,
`~/.claude/skills/`).

## Skills

| Skill | What it does |
| --- | --- |
| `anotherseoguru-setup` | Checks the connection, picks the Search Console site and keeps context between sessions |
| `anotherseoguru-seo-coach` | Not sure what to run? Start here |
| `anotherseoguru-top-fixes` | The fixes worth the most clicks, with the evidence and the number to watch |
| `anotherseoguru-fix-task` | Implements a task in your repo or CMS, verifies it live and marks it shipped |
| `anotherseoguru-weekly-report` | A plain-language weekly report from Search Console, SEO health, page changes and ranks |
| `anotherseoguru-ai-visibility` | How often ChatGPT, Gemini, Perplexity and AI Overviews cite you, and who they cite instead |
| `anotherseoguru-site-audit` | The latest crawl as a prioritized technical fix list, with schema and hreflang checks |

## Safe by design

Read tools never change anything. The only write tools update your AnotherSEOGuru App tasks, and
only with the tasks permission. A task is marked shipped only after the change is live, which starts
the before/after Search Console measurement.

## Ελληνικά

Έτοιμες ροές εργασίας SEO για Claude Code, Codex, Cursor και κάθε agent που διαβάζει `SKILL.md`.
Συνδέστε πρώτα τον MCP server του AnotherSEOGuru App (`https://app.anotherseoguru.com/mcp`) και
μετά τρέξτε `npx skills add otouristas/anotherseoguru-skills`. Τα δεδομένα έρχονται από το δικό σας
Google Search Console, και τα έργα στα ελληνικά παίρνουν brief στα ελληνικά.

---

AnotherSEOGuru App is a product of Touristas Technologies. MIT licensed.
