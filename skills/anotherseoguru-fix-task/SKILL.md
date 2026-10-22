---
name: anotherseoguru-fix-task
description: Take an AnotherSEOGuru App task, implement the SEO fix in the open repository or CMS, verify it is live and mark it shipped so the before/after measurement starts. Use when the user says "fix this task", "work through my SEO tasks" or sends a task link.
---

# Fix an AnotherSEOGuru App task

## Steps

1. Find the task: the id the user gave, else `get_agent_task_inbox` (tasks sent to this connection),
   else `get_tasks` with `status: open`. Ask which one if several fit.
2. Call `get_task_brief` with `mode: code` (or `mode: chat` when there is no codebase, only copy to propose).
3. Call `start_task` so the board shows the work is in progress.
4. Make the change exactly as the brief's implementation and acceptance checks describe. Keep the
   site's design, links and calls to action. Do not change prices or legal text unless the brief says so.
5. Add a short `add_task_note`: what you changed and where (pull request link if there is one).
6. Only after the change is live and verified (fetch the live URL and check the title, meta, H1,
   schema or content the brief targets), call `complete_task` with a one to five sentence summary
   and the changed URLs. This starts the before/after Search Console measurement.

## Rules

- Never call `complete_task` for a change that is not live.
- If a check fails or you are blocked, use `add_task_note` to say why and stop.
- For structured data changes, run `validate_schema` on the live URL before completing.
