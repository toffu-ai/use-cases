# Toffu use-cases

Content source for `https://toffu.ai/use-cases/<slug>`.

Each `<slug>.json` describes one landing page. The toffu-chat repo clones this
repo at build time (`scripts/fetch-content.js`) into `content/use-cases/`, and
the dynamic route `app/(marketing)/use-cases/[slug]/page.tsx` reads + renders
them.

Schema lives in `lib/use-cases/schema.ts` in toffu-chat (Zod). Invalid files
are skipped at build, not crashed on.

## Adding a new page

1. Add `<kebab-case-slug>.json` at the repo root.
2. Commit to `main`.
3. Vercel rebuilds toffu-chat via deploy hook; page is live in 1-3 min.

A hand-coded `app/(marketing)/use-cases/<slug>/page.tsx` in toffu-chat wins
the route match over the JSON. Pick a different slug to avoid being shadowed.
