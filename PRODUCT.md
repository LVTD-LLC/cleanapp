# Product

## Product Overview

PageFresh turns sitemap maintenance into a recurring review workflow. Users add sitemaps, PageFresh imports active pages, queues URLs for review on a cadence, and sends email digests with direct review links. The product replaces the spreadsheet/reminder-system version of website maintenance with a simple loop users can trust.

The public product name is PageFresh. The repository, Django project package, Docker services, database names, and some deployment resources still use `cleanapp`. Do not rename those technical surfaces unless a task is explicitly about a coordinated rename.

## Target Users

Primary users:

- Website owners who need recurring reminders to keep key pages current.
- Solo operators maintaining a small portfolio of owned sites.
- Small agencies responsible for multiple client sites.

Secondary users:

- Admin/operator users who need basic visibility into users, sitemaps, feedback, and scheduled jobs.
- Self-hosters deploying through Render, Docker Compose, or a Python/Django environment.

## Core Jobs

PageFresh should help users:

1. Add a sitemap quickly and know that pages were imported.
2. Group sites by client or workspace.
3. Decide how many pages each digest should surface and how often.
4. Receive a digest that is easy to scan by client and site.
5. Open a page from the email, review it in the real context, and mark it reviewed.
6. Keep billing and site limits understandable.

## Current Product Surface

The app currently includes:

- Landing, pricing, authentication, dashboard, sitemap detail, settings, admin, blog, and uses pages.
- Django Allauth username/email authentication with optional GitHub social login.
- Sitemap import through background tasks, including nested sitemap traversal.
- Page review queueing with cadence windows and per-sitemap page limits.
- Email digests grouped by client and site.
- Multiple email recipients per profile.
- Stripe Checkout, Billing Portal, webhook handling, and site limits for free/starter/agency plans.
- Soft archive behavior for sitemaps and pages.
- Session-authenticated Django Ninja endpoints for feedback, sitemap archive, bulk page state, and email preferences.
- PostHog/Plausible analytics hooks, Buttondown newsletter hooks, and Sentry/Logfire observability hooks.

## Business Model

PageFresh is self-serve SaaS with a free tier and paid site-limit tiers. Billing logic is centered on active sitemap count, plan keys, Stripe price IDs, and profile state transitions. Treat billing changes as product-sensitive because they affect access, trust, and paid conversion.

Plan names and defaults currently favor:

- Free: small initial usage.
- Starter: a handful of active sites.
- Agency: larger client portfolios.

## Product Principles

- The review loop is the product. Do not let new features obscure sitemap import, queueing, digest delivery, and reviewed state.
- Agencies are first-class users. Client labels, grouped digests, and multi-site scanning matter.
- Email is the primary workflow surface. The dashboard supports and configures the loop, but the digest drives recurring behavior.
- Trust beats novelty. Prefer clear state, predictable scheduling, and recoverable errors over clever UI.
- Keep the free/self-host path practical. Avoid changes that require paid infrastructure for small usage unless the task is explicitly about scale.
- Make external service failure understandable. Stripe, Mailgun, PostHog, Buttondown, S3/MinIO, Redis, and sitemap fetches should fail visibly in logs and gracefully in user flows.

## Anti-Goals

Do not turn PageFresh into:

- A full SEO crawler or audit suite.
- A CMS, content editor, or AI content generator.
- A project management system.
- A noisy analytics dashboard.
- A multi-channel notification platform before the email loop is excellent.
- A generic SaaS template with decorative metrics and vague productivity copy.

## UX Voice

The voice is plain, useful, and low-drama. Prefer concrete labels like `Add sitemap`, `Archive`, `Open pages`, `Pages per review email`, and `Review cadence`. Avoid hype and vague claims.

## Success Measures

When making product changes, optimize for:

- Time from signup to first sitemap added.
- Successful sitemap import rate.
- Due pages delivered per digest without repeats inside the same cadence window.
- Review completion from digest links.
- Clarity of plan limit and billing state.
- Low support burden for setup, email delivery, and webhook configuration.

## Accessibility

Target WCAG AA contrast for text and controls. Preserve keyboard navigation, visible focus states, reduced motion preferences, semantic form labels, and clear validation errors. Long URLs, email addresses, and client labels must wrap without breaking layout.
