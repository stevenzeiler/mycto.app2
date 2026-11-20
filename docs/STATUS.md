# Status

Last updated: 2026-11-20 (docs pass of the GitHub audit; nothing was run).

## What works

Unverified. The code is the upstream Vercel starter, which is known to work when Supabase and Stripe are configured; that has not been checked for this copy.

## Known broken or unverified

- Not run in this pass except where noted below.
- Build almost certainly fails without env vars: the code is byte-identical to walletbot.dev, whose `pnpm build` stops with `Error: supabaseUrl is required` at `/api/webhooks` when Supabase env vars are unset. Not built for this repo **(inference)**.
- The Vercel preview of the docs PR fails because `NEXT_PUBLIC_SUPABASE_URL` and the other vars from `.env.local.example` are not set in the Vercel project **(inference: Vercel logs not read)**. Not caused by this docs-only PR.
- Page title and metadata still say "Next.js Subscription Starter"; no mycto.app2 branding.
- No product features beyond the starter's pricing, sign-in and account pages.
- No tests, no CI (`.github/` is absent).
- Dependencies date from June 2024 (Next.js 14.2.3, Stripe 14.x); not audited for vulnerabilities.
- `package.json` has no name, description, license or engines.

## Next

1. Decide whether mycto.app2 is still a product; if not, archive it (Steven's call).
2. If kept: rename in `app/layout.tsx` and `utils/stripe/config.ts`, define the real offer, and add a one-pager.
3. Add `.github/` CI (lint and build) and a CHANGELOG once there is code of its own.

## Not yet from the standard

Missing: CONTRIBUTING.md, docs/ARCHITECTURE.md, docs/RELEASING.md, docs/decisions/, events/CATALOG.md, CHANGELOG.md, SECURITY.md, .github/, product/ONE-PAGER.md. LICENSE is present (upstream Vercel MIT).
