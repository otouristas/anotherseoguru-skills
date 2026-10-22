---
name: anotherseoguru-setup
description: Connect the AnotherSEOGuru App MCP server and choose the Search Console site to work on. Use first, or whenever an AnotherSEOGuru tool says it is not connected or you don't know which site_url to use.
---

# Set up AnotherSEOGuru App

These skills read your Google Search Console data, fix list, tasks and AI visibility through the
AnotherSEOGuru App MCP server. They do nothing without it.

## 1. Check the connection

Call `list_sites`. If the tool is missing or returns an authorization error, the server is not connected yet.
Tell the user to add it once (they need an AnotherSEOGuru App account with Search Console connected,
free sign-up at https://app.anotherseoguru.com/signup):

- Remote URL for any client that accepts one: `https://app.anotherseoguru.com/mcp` (OAuth, no token to paste)
- Claude Code: `claude mcp add --transport http --scope user anotherseoguru https://app.anotherseoguru.com/mcp`, then `/mcp`
- Codex: `codex mcp add anotherseoguru --url https://app.anotherseoguru.com/mcp`, then `codex mcp login anotherseoguru`
- Local-only clients: `npx -y mcp-remote https://app.anotherseoguru.com/mcp` as the command

Full per-client steps: https://anotherseoguru.com/en/platform/mcp#clients

## 2. Pick the site

From `list_sites`, ask which property to use when there is more than one. Remember the exact `site_url`
(for example `sc-domain:example.com`) and pass it to every later call.

## 3. Save context for later sessions

If you can write files, keep a short `anotherseoguru.md` in the working folder: the site_url, the
project's language (Greek projects get Greek briefs), the business goal and anything the user said
not to touch. Read it at the start of every AnotherSEOGuru workflow.

## Rules

- Read tools never change anything. Task tools (`start_task`, `add_task_note`, `complete_task`) only
  update AnotherSEOGuru App tasks and need the tasks permission.
- Never invent numbers. Every figure you report comes from a tool result, with its date range.
