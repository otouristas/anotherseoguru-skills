---
name: anotherseoguru-top-fixes
description: Find the SEO fixes worth the most clicks for a site from its own Search Console data, explain each in plain language and suggest what to do first. Use when the user asks what to fix, where the quick wins are, or why traffic is flat.
---

# Top SEO fixes from Search Console

## Steps

1. Make sure you know the `site_url` (run the `anotherseoguru-setup` skill if not).
2. Call `get_opportunities` with `site_url` and `limit: 10`. For a focused question pass `kind`:
   `striking_distance`, `ctr_gap`, `decay`, `cannibalization` or `content_gap`.
3. For the top 3 items, confirm the numbers with `get_performance` filtered by `page_contains` or
   `query_contains` (28 days, compare on).
4. Present a short table: fix, page, the evidence (position, impressions, CTR), estimated extra clicks
   per month, and the leading indicator to watch with its check date.
5. Recommend one fix to start with and say why in one sentence.

## Output rules

- Lead with the answer: "Start with X: it is worth about N clicks a month."
- Estimates are estimates. Say so once, next to the figure.
- Use the dates the tool returned. Search Console data ends about 3 days ago.
- If the user wants it done, hand over to `anotherseoguru-fix-task`.
