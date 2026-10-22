---
name: anotherseoguru-weekly-report
description: Write a plain-language weekly SEO report for a site from Search Console, SEO health, page changes and live ranks in AnotherSEOGuru App. Use for weekly or monthly updates, client reports or "how did we do".
---

# Weekly SEO report

## Data to collect

1. `get_performance` with `dimension: date`, `days: 28`, compare on: totals and the change.
2. `get_performance` with `dimension: page`, `limit: 10`: pages that gained and lost the most.
3. `get_seo_health`: the score, the categories that moved and categories with no data.
4. `list_page_changes` with `days: 7`: title, meta, H1, canonical, noindex or redirect changes.
5. `get_live_ranks` with `limit: 20`: tracked keywords that moved.
6. `get_tasks` with `status: done`: what shipped this period.

## Report shape

- One sentence verdict first (clicks up or down, by how much, over which dates).
- Three bullets: what helped, what hurt, what changed on the site.
- A table of the five pages that moved most.
- Next week: the top two items from `get_opportunities`.

Write for a business owner, not an SEO. Explain a term the first time you use it. Never fill a gap
with a guess: if a tool has no data for a section, leave the section out.
