# The Ninth Chamber

**Source-of-truth repository for The Ninth Chamber web application.**

## Baseline status — 23 October 2026

This repository was empty at integration start. This initial commit establishes source-control policy and CI/security scaffolding only; it **does not** represent a functioning Build 44 application. The Build 44 source archive and approved visual production assets must be migrated without recreating or silently changing them.

## Launch contract

- Complete Dossier: **$14.99**, one-time.
- One complimentary Monthly Examination: **next full calendar month**.
- Further Monthly Examinations: **$4.99/month**, only with affirmative opt-in. No automatic subscription.
- Dossiers and issued examinations retained in the customer's private Archive and available for authenticated download; notify by email when ready.
- Historical visual art and approved layouts are not to be replaced.
- Deterministic calculations must be validated before interpretive prose or publication.

## Engineering rules

1. GitHub `main` is the authoritative code baseline *after* the actual Build 44 migration and validation. Until then, this repository is an integration scaffold, not a production application.
2. Commit source code and approved nonsecret assets; never commit live credentials, personal data, private reports, payment information, or generated build artifacts.
3. Develop on feature branches and use pull requests; require CI checks after the project is migrated. Do not deploy unvalidated code.
4. Database schema changes require versioned migrations and rollback consideration. Generated customer records and paid artifact editions are immutable.
5. Stripe entitlements come only from verified, idempotent server webhooks. Never trust client purchase status. Subscription continuation requires explicit opt-in.
6. Server authorization plus RLS protects customer Records and Archive content. Storage buckets must remain private.
7. Protect period-authentic First Arrangement, cover, interior, Chinese, Lunar, Convergence and Closing Examination art/layouts.

## Preparing the code migration

Export the latest **Build 44** source as a ZIP (or full source tree) and place it into this repository via a reviewed migration PR. Preserve its lockfile and versioned reference assets. Audit the archive for secrets and personal data before the first push. CI currently flags the missing application and **skips** application build/test steps rather than falsely presenting green checks as successful builds.

Proposed V1 stack from the approved architecture: Next.js/TypeScript, Supabase, Stripe, OpenAI Responses API, Trigger.dev, Resend, and controlled HTML/CSS PDF generation.

**Important:** Green workflow execution before the migration means only that repository scaffolding executed; it does **not** attest to TypeScript, tests, or build success.
