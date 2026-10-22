---
name: anotherseoguru-site-audit
description: Turn the latest AnotherSEOGuru App site crawl into a short, prioritized technical SEO fix list, including structured data and hreflang checks. Use for "audit my site", technical SEO questions or before a redesign launch.
---

# Technical audit

## Steps

1. Call `get_site_audit_findings` with `category: all`, `limit: 30`, `examples: 3`.
2. Group the findings into: blocks indexing, wastes crawl or links, hurts snippets, everything else.
3. For schema issues, run `validate_schema` on one example URL to show the exact error.
4. For multilingual sites, call it again with `category: hreflang` and list missing return links,
   invalid codes and missing x-default.
5. Cross-check impact: for the top issues, `get_performance` with `page_contains` on an affected URL
   shows whether the page earns clicks worth protecting.

## Output

A numbered list, worst first: issue, pages affected, one example URL, the fix in one line, and
whether it needs a developer. Stop at ten items.
