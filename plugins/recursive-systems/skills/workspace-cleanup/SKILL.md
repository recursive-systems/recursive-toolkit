---
name: workspace-cleanup
description: Audit AI workspace skills, project instructions, and supporting files for duplication, conflicts, stale guidance, and potential retirement. Use when the user asks to clean up these resources; propose changes first unless edits are already authorized.
---

Audit this project's AI skills, instructions, and supporting files. Recommend changes that reduce unnecessary context and maintenance while preserving useful behavior.

Identify the models and agent environments currently using these resources from available configuration and session information. If the current model or model set is unclear, ask the user. Consult the latest official prompting guidance for those models and versions. Where model-specific guidance is unavailable, fall back to the latest official OpenAI and Anthropic guidance, noting relevant differences across the model set. Cite sources and the date checked; disclose when current guidance cannot be verified.

Look for obsolete guidance, conflicting rules, duplication, overly broad skill triggers, unused files, and unnecessary procedural constraints. Distinguish what is installed or discoverable from what actually loads into context. Check dependencies and usage before recommending removal; missing references alone do not prove something is unused.

Favor clear goals and essential constraints. Leave room for model judgment, emergent behavior, and useful approaches the author did not anticipate. Choose your own audit method and recommend removing prescribed steps that serve no demonstrated need. Preserve project requirements and user preferences; shorter instructions are not automatically better.

Give a concise proposal with the affected files, evidence, expected benefit, and uncertainty. Keeping things unchanged is a valid outcome. Apply changes when authorized, preserving unrelated work and a way to undo them. Verify affected workflows; use representative tasks to assess claimed behavioral improvements. Include user-wide resources only when they are within the requested scope.
