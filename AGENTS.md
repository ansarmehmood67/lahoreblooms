# AGENTS.md — weddingroomdecoration.com (Astro)
Purpose: This repo powers a LIVE, ranking website. The homepage is already getting daily impressions and leads.
Your job is to make additive, SEO-safe changes. Avoid refactors unless explicitly requested.

---

## 0) Non-negotiable safety rules (SEO / revenue protection)
- ✅ DO NOT change or remove existing URLs/routes (especially `/` and `/product/*`).
- ✅ DO NOT delete, rewrite, or reorder existing homepage sections in a way that changes meaning or layout.
- ✅ DO NOT rename files that map to routes.
- ✅ DO NOT change existing product slugs or product detail route params.
- ✅ DO NOT introduce new frameworks or major dependencies in the first PR.
- ✅ Prefer additive changes (new files/pages/components) and minimal wiring.
- If any change risks altering homepage output, **skip it** and propose a safer alternative.

---

## 1) Current business + entity requirements
- Brand entity on this site must be: **Lahore Blooms** (service: Wedding Room Decoration Lahore).
- Phone/WhatsApp must remain consistent wherever used (reuse existing config/value).
- Tone: professional, local Lahore service, clear pricing ranges, WhatsApp-first.

---

## 2) Tech stack + routing
- Framework: **Astro**
- New routes must be created under: `src/pages/`
- Do NOT break trailing-slash behavior:
  - If existing site uses trailing slashes, keep them consistent on new pages.
- Do NOT alter existing build configuration unless requested.

---

## 3) Phase 1 scope (STRUCTURE FIRST only)
This PR is STRUCTURE-FIRST only:
- Create new pages as skeletons (headings + short intro).
- Add shared Header/Footer for new pages (multi-page navigation).
- Add a BaseLayout for new pages (SEO head support).
- NO long copy, NO heavy SEO content, NO big FAQ libraries yet.
- No product filtering system refactor in Phase 1.

Allowed content on new pages:
- 100–150 word intro (AEO-style “Quick Answer”)
- headings + 1–2 lines per section
- 2–3 sample FAQs only (full FAQs later)

---

## 4) Required new routes to create (exact slugs)
Create these pages (skeleton only):

Category hubs:
- `/masehri-design/`
- `/masehri-design-simple/`
- `/masehri-design-artificial/`
- `/masehri-design-latest/`
- `/saj-design/`
- `/simple-wedding-room-decoration-pakistani/`
- `/luxury-wedding-room-decoration/`
- `/bridal-room-decoration/`

Info / AEO:
- `/wedding-room-decoration-items/`

Trust / conversion:
- `/gallery/`
- `/wedding-room-decoration-prices/`
- `/about/`
- `/contact/`

---

## 5) Standard page skeleton (must be consistent on all new pages)
Each new page must include, in this order:

1. H1 (topic-specific)
2. Short “Quick Answer” intro (100–150 words max)
3. H2: Starting Price / Range (placeholder)
4. H2: What’s Included (placeholder bullets)
5. H2: Designs / Products (placeholder only; no filtering implementation yet)
6. H2: Best For
7. H2: How Booking Works (3 short steps)
8. H2: FAQs (only 2–3 sample Qs)
9. CTA block: WhatsApp + “Get Prices” button (link to prices/contact)

---

## 6) Navigation rules (very important)
- Convert site navigation to multi-page links for NEW pages:
  - Home `/`
  - Prices `/wedding-room-decoration-prices/`
  - Gallery `/gallery/`
  - Masehri `/masehri-design/`
  - Contact `/contact/`
- Keep WhatsApp CTA visible in header.
- DO NOT remove existing homepage anchors; just avoid using them as the primary nav for new pages.

Important: If homepage currently uses a special header/footer, do NOT refactor it in Phase 1.
Create new components instead (e.g., `SiteHeader`, `SiteFooter`) and use them on new pages.

---

## 7) SEO head requirements (BaseLayout)
BaseLayout must support:
- `<title>`
- `<meta name="description">`
- canonical URL (optional prop)
- OG tags (basic)
No heavy SEO tooling in Phase 1 unless already present.

---

## 8) What NOT to do in Phase 1
- ❌ No changes to homepage copy beyond tiny safe additions (and only if required).
- ❌ No big content generation (no 1000+ word pages yet).
- ❌ No new sitemap plugin unless the project already uses one.
- ❌ No CSS/JS refactors that affect global styling.
- ❌ No changes to product route logic.

---

## 9) Build & QA requirements
Before opening a PR:
- Build must succeed.
- Homepage must render the same (visually & structurally) as before.
- Product pages `/product/*` must still work.
- All new pages load without 404s.
- Navigation links work.

If repo has scripts, run them (prefer the existing standard commands):
- `npm run build` (or `pnpm run build`)
- `npm run dev` sanity check (if required)

---

## 10) PR rules (deliverable format)
Open a PR titled:
**"Structure-first multipage expansion (Astro)"**

PR must include:
- List of routes added
- Files added/changed
- Explicit confirmation:
  - homepage unchanged (or describe minimal safe change)
  - product routes unchanged
  - build passes
- Keep diff mostly additive (new files).

---
