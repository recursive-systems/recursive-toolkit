---
name: business-loop-map
description: Map a business's or team's recurring work as loops, each with a trigger, steps, checks, a result, and the point where a person must step in. Gather evidence from available project files, connected tools, and session history the user puts in scope, then recommend which loops to run with AI first. Use when the user asks which work to automate, where AI fits their operations, or for a loop map, workflow audit, or automation candidates. Recommendations only.
---

Map the recurring work in this business or team as loops, and recommend which loops to run with AI first. A loop is work that repeats: something triggers it, steps follow, a check shows whether it was done right, it produces a result, and it hands off to a person when it cannot finish.

Before reading content deeply, inventory only sources actually available in this environment. Use names, directory listings, connector metadata, and other metadata first; do not imply access that has not been established. Include available project files and folders, connected services, session history or memory the host exposes, and the user. Tell the user what you found and ask one focused scope question. Explicitly name any personal data, customer data, mailboxes, calendars, date ranges, or conversation transcripts that need permission, and do not read their content until the user puts them in scope. This scope question is the only required pause.

Gather broad but bounded evidence. Choose a relevant sample rather than reading everything. Inspect no more than 10 items or records from a source unless the user expands the scope; in a dataset such as a CSV or spreadsheet, each row is a record, so inspect no more than 10 rows rather than treating the whole dataset as one item. The limit is collective across all delegates: their combined reads from a source must stay within the same 10-record bound, not 10 records per delegate. Report how many you inspected and how many were available when known. For each loop, stop as soon as you can identify its trigger, steps, check, result, and human handoff and cite two real occurrences. If two occurrences or a check are not available within the sample, stop anyway and mark the gap; never invent an occurrence or other evidence. You may ask up to two more focused questions for important missing facts, but answering them is optional: proceed with a partial map and mark the gaps. When subagents are available, give each an independent source area within the same scope and collective limits, then reconcile their findings.

For each candidate loop, record its trigger, steps and who performs them, tools touched, frequency, result, check, failures, and human handoff. Include duration only when a source documents an observed duration; never estimate it. Then consider how much of the result a rule can check, the upside of doing it better rather than only cheaper, the cost of an error, and where a person must decide.

Use four plain-language stages:

1. AI helps with individual tasks.
2. AI handles larger parts of the workflow.
3. People set rules for what runs, who approves it, and what gets checked.
4. The loop runs on its own, with a person stepping in at defined points.

Say where each loop is today and what the next stage would require. If the evidence does not establish its current stage, mark the stage as unknown and explain what evidence would establish it; do not invent a current stage. Do not assign scores.

Present loops in priority order based on how often they run, how checkable the result is, and how small and safe the first step is. Explain the order. For each loop, give the evidence; label observations, inferences, and unverified points; write out the loop; say what AI would do and where a person takes over; name the check that keeps it honest; recommend the smallest useful first step; and explain how to tell whether it worked. Recognize loops that already work well. Leaving a loop unchanged can be the right recommendation. Do not include time estimates or maturity scores. Do not reproduce customer details, credentials, private messages, or other sensitive content; describe patterns instead. Write plainly and adapt detail to the reader.

This is a recommendations-only review. Do not change files, settings, or data; run scripts; create records; or send messages. Use non-destructive reads only. Never make a write call to a connected service. After presenting the finished map, offer to save it as one project file. That explicitly approved local save is the only exception: create the file only after the user consents.
