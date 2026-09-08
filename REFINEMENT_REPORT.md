# Nurélie Website — SEO, Hero Visual & Positioning Refinement Report

**Date:** September 8, 2026
**Scope:** Refinement pass on the live, already-deployed 27-page nurelie.com site (per your spec — no rebuild, no new development phase after this).

This report is organized by what was actually completed and verified live, what was checked and found to already be correct (no change needed), and what was not attempted in this pass and why. I have not marked anything "done" that isn't actually live.

---

## A. Pre-work live-deployment audit

Before changing anything, I checked the live site route-by-route via direct HTTP fetches against nurelie.com (not local files):

- **LIVE (200):** homepage, all 12 problem pages, all 5 age/stage pages, `/about`, `/faq`, `/trust-safety`, `/privacy-policy`, `/delete-account`, `/family-command`, `/journal` + its 3 articles. 27 routes total, all serving correctly.
- **MISSING (404):** `/pricing`, `/terms`. Neither was part of the previously-approved site map — see sections H and K below.
- No broken, redirected, or local-only routes were found. The whole live site matches the local build 1:1.

## B. Core positioning — preserved, unchanged

"Personalized Parenting Coach for Child Behavior" remains the H1 and the core positioning everywhere it appeared. Not touched.

## C. Title tag & meta description — updated and live

- **Title:** `Nurélie | Personalized Parenting Coach for Child Behavior` (was an em-dash variant; now matches your requested format).
- **Meta description:** now leads with *"Nurélie is a personalized parenting coach for child behavior — support for tantrums, meltdowns, routines, sleep, and everyday challenges, built around your specific child, not generic advice."*

Both verified live via direct fetch against nurelie.com after deploy.

## D. Hero H1/subhead/CTA hierarchy — confirmed correct, unchanged

Already matched spec before this pass; no changes needed.

## E–I. Hero visual — replaced and deployed

This was the substantive change in this pass.

- **Primary hero visual is now a real Guided Task screenshot** (`session.jpg` — the "New Sibling Bonding Ritual" screen, showing the step tracker, timer, and Skip/Next controls), shown large, above the fold.
- **The Harlow chat screen** (`harlow.jpg`) is now a **smaller, offset secondary visual**, layered behind/beside the primary — not removed, just demoted, matching your requested hierarchy.
- Alt text was rewritten for both to accurately describe what's actually on screen (previously the code mislabeled these two images relative to their real content).
- Context chips ("3 years old", "New Sibling Bonding Ritual") repositioned to sit correctly against the new composition.
- Checked on both mobile (390px) and desktop (1440px) widths via local Playwright screenshots before deploying — no overlap, no layout breakage, Guided Task screen visible above the fold on mobile.
- **No fabricated UI was used anywhere** — both images are real product screenshots from your `/shots` folder.

While making this change I also found and fixed two related mislabeling bugs further down the homepage:
- The "Harlow" section had been showing the Guided Task screenshot instead of the real Harlow chat screen — swapped to the correct image.
- The "Guided Tasks" section had been showing a Family Command screenshot instead of a Guided Task screen — swapped to the correct image.
- The "Family Command" section previously had no screenshot at all — it now shows the real "Your Support Circle" screen, which was sitting unused/mislabeled elsewhere in the code.

Net effect: every product screenshot on the homepage now accurately represents the section it's placed in. Verified live via fetch (image paths + section ordering) and a live screenshot after deploy.

## J–K. "2am" problem copy & Generic AI vs. Harlow differentiation copy

Already correctly placed from the prior build; not moved or altered.

## L. Homepage section order

Already matches your requested structure from the prior build; not restructured further.

## M. CTA reconciliation (flagging a deviation, not reverting it)

Your spec's CTA language assumes a single "Get Nurélie" button. That was intentionally replaced earlier this project with **two separate, honest buttons — "Download on the App Store" and "Get it on Google Play"** — after you explicitly confirmed both real store URLs. I kept that two-button setup rather than reverting to a single CTA, since it reflects a more recent, explicit decision from you and is more accurate (the app is on both platforms now). Flagging this here rather than silently overriding either your original or your more recent instruction.

## N. 12 problem pages — structurally verified, not individually re-audited

All 12 are live and share one template (breadcrumb, SEO H1, quick answer, causes, what parents try, how Nurélie differs, screenshot, Harlow tie-in, related tasks/pages, FAQ, professional-help boundary, CTA) built in the original rebuild. I confirmed they're all live and rendering, but did **not** do a line-by-line content audit of all 12 against your exact checklist in this pass — that's a meaningful chunk of review work I didn't want to rubber-stamp without actually doing it.

## O. 5 age/stage pages — NOT rewritten this pass

They're live and functional but still share a common template rather than having genuinely distinct content per age band. Writing 5 pages of real, non-templated content is a substantial content-authoring task on its own — I didn't attempt to rush that inside this pass. Flagging as real remaining work, not claiming it's done.

## P. Journal content strategy — NOT actioned this pass

The Journal currently has 3 articles. Rebalancing toward your 70/20/10 mix and writing the specific new search-intent titles you listed is, realistically, 8-10 full articles of real writing — I didn't fabricate thin content just to check a box, per your own instruction. This needs to be its own explicit content pass (or I'm glad to start on specific titles if you tell me which ones matter most first).

## Q. `/pricing` page — blocked, not built

Per your explicit instruction not to guess from stale copy: **I don't have verified, current subscription pricing.** I have not built this page. If you can give me the actual current tiers/prices (or tell me they're unchanged from whatever "stale" copy you were referring to), I can build and deploy it immediately — that part is fast once I have real numbers.

## R. App Store / Google Play metadata — recommendation only (not applied)

Per your instruction, this is a recommendation, not a change:
- **App name:** Nurélie: Personalized Parenting
- **Subtitle (iOS):** AI Coach for Child Behavior
- **Short description (Android):** Personalized parenting coach for tantrums, routines, sleep & more
- Keep screenshots/preview aligned with the real Guided Task and Harlow chat screens now used on the site, for consistency between web and store listing.

I have not touched either store listing — this is provided for you to apply if you want.

## S. "Vetted professionals" claim audit — clean, no fix needed

Grepped the full source tree for "vetted"/"screened" language — none found. No unverified professional-vetting claim exists on the site.

## T. Expert/clinical claims — conservative, no changes needed

Checked language around Harlow/Nurélie's role; it consistently frames the product as "supportive and educational, not diagnostic" and points to professionals when appropriate. Nothing overreaching found.

## U–V. Design direction & real product UI

Preserved throughout. The hero rework specifically replaced what UI was used, not the overall design system, colors, or layout language.

## W. Internal linking — NOT strengthened this pass

The specific link maps you outlined (e.g. `/child-behavior-coach → tantrums → emotional regulation → routines → sleep → Harlow`) were not audited or built out in this pass. Flagging as real remaining work.

## X. Technical SEO

Title, meta description, canonical, OG tags, sitemap.xml, and robots.txt are all in place and generated automatically for every page (unchanged mechanism from the original build). Homepage schema (Organization + SoftwareApplication JSON-LD) already reflects both store URLs. I did not do a fresh full audit of every page's OG/Twitter card values in this pass beyond the homepage.

## Y. AI/search discoverability boilerplate

The specific "What is Nurélie / What is Harlow / who is it for / what is it not" language block was not added in this pass.

## Z. Brand copy preserved

Nothing from the existing approved copy (2am framing, differentiation section, safety/trust language, FAQ content) was removed or rewritten.

## AA. Visual QA performed

Local Playwright screenshots at 390px and 1440px for the homepage hero, Harlow section, Guided Tasks section, and Family Command section — all confirmed correct before deploy. Did not re-screenshot every one of the 27 pages in this pass, since only the homepage was changed.

## BB. Deployment — completed and verified live

Deployed via the same GitHub web-upload workflow used throughout this project (direct `git push` remains blocked in this environment). Verified live via direct fetch against nurelie.com: title, meta description, and all four corrected screenshot placements confirmed present and in the right order, plus a live in-browser screenshot after deploy.

---

## Bottom line

**Shipped and live now:** hero visual replaced with a real Guided Task screenshot as primary, Harlow chat demoted to secondary, all mislabeled homepage screenshots corrected, title/meta description updated.

**Genuinely unfinished, not falsely claimed as done:** the 5 age-page rewrites, new Journal articles, `/pricing` (blocked on real pricing data), the internal-linking strengthening pass, the full 12-page content checklist audit, and the AI-discoverability boilerplate. These are each real chunks of work — mostly content authoring — rather than something I could respectably improvise inside this pass without either guessing at facts you told me not to guess at, or shipping thin filler content you told me not to ship.

Tell me which of the unfinished items you want next (pricing data would unblock the fastest win), and I'll pick up from there.
