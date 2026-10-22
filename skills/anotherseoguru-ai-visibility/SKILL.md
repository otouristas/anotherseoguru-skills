---
name: anotherseoguru-ai-visibility
description: Check how often ChatGPT, Gemini, Perplexity and Google AI Overviews cite a site for its tracked prompts, who they cite instead, and what content would close the gap. Use for GEO / AEO questions and "do AI assistants mention us".
---

# AI visibility (GEO / AEO)

## Steps

1. Call `get_ai_visibility_summary` with the `site_url` and `days: 30`.
2. Report the citation rate overall and per model, the average citation position and the competitor
   domains cited most.
3. List the tracked prompts that never cite the site. For each, call `get_performance` with
   `query_contains` on its main term to see whether the site already ranks in Google for it.
4. Suggest one concrete content change per gap: the page to improve or create, the question it must
   answer directly in the first lines, and the facts or structured data that make it citable.
   Check existing structured data with `validate_schema` on that URL.

## Rules

- Only report prompts and models the tool returned. Do not run your own AI queries and present them as tracked data.
- A citation rate is a sample over the tracked prompts, not a share of all AI answers. Say so once.
