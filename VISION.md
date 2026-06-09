# Vision

PageFresh exists because stale website content is usually an operational problem, not an ideas problem. People know their pages should be reviewed, but the work lives in forgotten spreadsheets, calendar reminders, or someone's memory. PageFresh makes that maintenance loop explicit, scheduled, and easy to finish.

The product should become the small, dependable system a website owner or agency trusts to answer: which pages need attention, for which client, and what should I review next?

## Direction

The near-term product is intentionally narrow:

- Import pages from sitemaps.
- Keep an active review queue.
- Send useful email digests on a configurable cadence.
- Group work by client/site for agency maintenance.
- Let users mark pages reviewed from the real page context.
- Keep billing, plan limits, and setup understandable.

The long-term direction is a maintenance operating layer for small web portfolios. PageFresh can grow into better prioritization, freshness signals, review history, lightweight reporting, and team workflows, but only if those features strengthen the recurring review loop.

## Principles

- Be useful before being clever.
- Make routine maintenance feel calm and finite.
- Keep the user close to the real page they are reviewing.
- Prefer clear schedules and states over opaque automation.
- Treat email as a high-signal workflow surface, not a dumping ground.
- Make agency use natural without making solo use heavy.
- Keep self-hosting and small deployments practical.

## Current Focus

- Reliability of sitemap import and nested sitemap handling.
- Deterministic review queues that do not repeat pages inside the same cadence window.
- Digest quality: grouped, scannable, and action-oriented.
- First-run onboarding and empty states.
- Billing correctness, site limits, and Stripe state transitions.
- Clear settings for email recipients, timezones, cadence, and pages per review email.
- Operational visibility through logs, admin views, and focused tests.

## What We Will Not Build For Now

- A full SEO audit/crawling suite.
- A CMS or page editor.
- AI content generation as a default workflow.
- Heavy project management, assignments, or kanban boards.
- Broad notification channels before email is excellent.
- Decorative analytics that do not change maintenance behavior.
- Complex enterprise permission models before small teams and agencies are solid.

This list is a guardrail, not a permanent ceiling. New features should explain how they improve the core review loop before they add surface area.
