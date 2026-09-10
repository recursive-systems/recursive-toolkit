---
name: app-maturity-review
description: Review an app built with AI and prioritize practical improvements to its architecture, database, tests, delivery, monitoring, and customer usage measurement. Use when the user asks for an app maturity or engineering readiness review; recommendations only, with no time estimates.
---

Review my app and recommend practical improvements to its design, development, and operation. Help me discover engineering concerns I may not know to ask about.

Understand the app’s purpose, users, current stage, and intended next steps. Use available project context and tools to inspect how it is built, tested, deployed, and maintained. Ask focused questions where information is missing. Distinguish observed problems from assumptions and things you could not verify.

When subagents are available, use as many as can usefully analyze independent areas in parallel, within the available limits. Give them focused scopes, then reconcile their findings into one review.

Use your judgment to explore relevant areas, including:

- Planning and change management: tracking bugs and features, reproducible bug reports, clear acceptance criteria, and manageable changes.
- Application design: cohesive responsibilities, loose coupling, appropriate boundaries, duplicated business logic, and useful abstractions.
- Database design: data relationships, integrity constraints, access patterns, indexes, and migrations.
- Testing: appropriate unit, integration, end-to-end, and acceptance tests, with realistic test data and coverage of important failure paths.
- Delivery: version control, automated build and test checks, CI/CD, development and production separation, preview or staging environments, configuration, and recoverable releases.
- Operation: authentication and authorization, secrets, input validation, dependency maintenance, error handling, backups and restoration, and useful documentation.
- Reliability and monitoring: availability, errors, response times, failed background jobs, external dependencies, and operating costs. Consider useful logs, metrics, and traces, actionable alerts, and who responds when something goes wrong.
- Customer usage and product feedback: understand whether users reach the intended outcome, where they get stuck or leave, which features they use, and whether they return. Consider meaningful events, funnels, retention, and feedback channels. Tie each measurement to a decision it would inform; collect only needed data and avoid recording secrets or sensitive content.

Treat these as areas to investigate, not requirements every app must satisfy. Account for capabilities already provided by its platform. Consult current official documentation when recommendations depend on a particular technology or service.

Scale recommendations to the app’s purpose, risks, and maintenance capacity. Recommend structural changes when they address a concrete problem or a likely near-term need. Explain the benefit and tradeoff. Favor the simplest effective design; avoid abstractions, layers, or rewrites introduced solely to satisfy a pattern. Similar-looking code does not always need to be consolidated.

Present recommendations in priority order, based on impact, risk, and dependencies. Explain each priority. For each recommendation, identify the evidence, explain a concrete consequence in plain language, suggest the smallest useful improvement, and describe how we would know it is complete. Distinguish what matters now from what can wait. Do not include time estimates. Recognize what already works; avoid unsupported maturity scores or claims that the app is production-ready.

Respond concisely and use progressive disclosure. Explain unfamiliar concepts as they arise, adapting the pace and detail to my experience and responses.

This is a review only. Do not modify the app, create issues, change configuration, or deploy anything. Use non-destructive inspection and checks; ask before any check that could alter data or affect a live service.
