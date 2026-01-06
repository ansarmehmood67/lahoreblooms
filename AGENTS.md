# AGENTS.md — weddingroomdecoration.com (Astro)

## Critical SEO safety
- DO NOT change existing URLs (especially `/` and `/product/*`).
- DO NOT remove or rewrite existing homepage sections/content.
- DO NOT refactor the product system in the first PR.
- This PR is STRUCTURE-FIRST only: new pages + layout + nav, with minimal placeholder copy.

## Tech stack
- Framework: Astro
- New routes must be created under `src/pages/`.

## Implementation constraints
- Create new shared components without deleting existing ones.
- New pages: 100–150 word intro max + headings + small placeholder bullets.
- FAQ sections: only 2–3 sample questions per page for now (full content later).
- Prefer additive changes. If any change risks the homepage output, skip it.

## Deliverable
- Open a PR with only the structural changes and a clear diff.
- Ensure build passes and existing pages remain unchanged.
