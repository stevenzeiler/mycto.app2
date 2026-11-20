# AGENTS.md

## Stack
Next.js 14 (app router), React 18, TypeScript, Tailwind, Supabase (`@supabase/ssr`), Stripe. Package manager: pnpm.

## Layout
- `app/`: routes (`/`, `signin`, `account`, `auth/*`, `api/webhooks`)
- `components/ui/`: UI components
- `utils/`: Supabase, Stripe and helper code
- `supabase/`: config, migration, seed; `schema.sql`, `types_db.ts` at root
- `fixtures/`: Stripe fixtures

## Commands
`pnpm install`, `pnpm dev`, `pnpm build`, `pnpm lint`, `pnpm prettier-fix`, `pnpm supabase:start`, `pnpm supabase:reset`, `pnpm stripe:listen`, `pnpm stripe:fixtures`.

## Rules
- Never commit secrets or `.env*` files with values; document env var names only.
- Use Conventional Commits.
- Keep docs/STATUS.md current when behaviour or state changes.
- Regenerate `types_db.ts` with `pnpm supabase:generate-types` after schema changes.
