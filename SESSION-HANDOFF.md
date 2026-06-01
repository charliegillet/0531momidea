# Session Handoff — Small Business Website Outreach

> **Purpose of this file:** A complete context export so a brand-new Claude Code
> session (e.g. on a laptop) can pick up exactly where the previous phone session
> left off. Hand this file to the new session and say "read SESSION-HANDOFF.md and
> continue."

---

## 0. Quick start for the new session

1. You are in the repo `charliegillet/0531momidea`.
2. Work happens on branch **`claude/small-business-outreach-ideas-gW6fV`**. Make sure
   you're on it: `git checkout claude/small-business-outreach-ideas-gW6fV && git pull`.
3. Read this whole file, then read the existing deliverables (listed in §3).
4. Pick up from **§5 (Next steps / open offers)**.
5. Commit + push to the same branch when done. Do **not** open a PR unless asked.

---

## 1. The user & the goal

- **User:** Charlie (charlie.gillet1@gmail.com).
- **Business idea:** Cold-call small/local businesses, offer to build them a simple
  website, and get paid **only after** the site is built and approved (pay-on-delivery,
  low flat price). The whole point is removing risk for the business so they say yes.
- **The user's stated plan:** Call → ask if they want a website → build it → ask for
  money only after it's built.
- **Tone the user wants:** Fast, action-oriented. In the phone session they said
  "do everything you can, don't ask for approval, do whatever is recommended." They
  value speed and concrete, usable deliverables over discussion.

---

## 2. What we've done so far (full session recap)

The phone session produced two rounds of work:

**Round 1 — Strategy & scripts.** Built a full outreach playbook: expanded the user's
target-business list with ~80 more candidates, documented how to find leads (Google
Maps trick: target listings with no website), wrote phone scripts + objection handling,
pricing strategy (build is the hook, recurring hosting is the real income), build-fast
tactics, a full call→cash workflow, and a quick-start checklist. Also created
copy-paste text/email templates and a lead-tracker spreadsheet.

**Key strategic insight captured:** The #1 risk in this model is doing the work then
not getting paid. The defense (documented throughout): **build on your own
subdomain/staging, show a preview at a temp URL, and only connect their real domain +
hand over logins AFTER payment.** Optionally take a tiny ($25–50) deposit and confirm
the payment method during the first call.

**Round 2 — A reusable website template.** Built a single-file, config-driven HTML
template so the user can spin up a client site in 5–15 minutes (edit one `CONFIG`
block → save → refresh). Includes click-to-call, mobile responsive, services, hours,
reviews, gallery, map embed. Shipped with two filled-in examples (plumber + taco
restaurant) to prove the same template works across industries, plus a README with
the clone-per-client workflow and free hosting instructions (Netlify Drop / GitHub
Pages / Cloudflare Pages).

Both `CONFIG` blocks were validated as syntactically valid JavaScript.

---

## 3. Files currently in the repo (on the working branch)

| File | What it is |
|---|---|
| `small-business-website-outreach.md` | **The master playbook.** Core model + payment-risk defenses; full target list (user's 16 + ~80 more); how to find/qualify leads; phone scripts; objection cheat-sheet; pricing; build-fast tactics; call→cash workflow; quick-start checklist; legal/trust notes. |
| `copy-paste-templates.md` | Ready-to-send: confirmation text, preview text, payment-due text, follow-up, review/testimonial ask, cold email, elevator pitch. |
| `lead-tracker.csv` | Spreadsheet template (open in Sheets/Excel) with columns + one example row. |
| `template/index.html` | The reusable single-file website template (also the Acme Plumbing demo). Edit the `CONFIG = {}` block at top. |
| `template/example-restaurant.html` | Same template, filled in as "Casa Verde Tacos" — proves cross-industry range. |
| `template/README.md` | How to clone the template per client; Google Map embed steps; free hosting options; payment-protection tip. |
| `README.md` | Original repo readme (untouched placeholder from initial commit). |
| `SESSION-HANDOFF.md` | **This file.** |

### Git state
- Branch: `claude/small-business-outreach-ideas-gW6fV` (pushed to origin).
- Commits so far:
  - `939fa6f` Initial commit
  - `2a13f61` Add small business website outreach playbook, scripts, and lead tracker
  - `8217c8a` Add reusable single-file local business website template + restaurant example
  - (+ a commit adding this handoff file)
- Working tree was clean before this handoff commit.

---

## 4. How the template works (so the new session can extend it)

- `template/index.html` is fully self-contained: `<head>` SEO tags, a `CONFIG` JS
  object, inline CSS in `<style>`, the HTML skeleton with empty elements, and a render
  script at the bottom that populates everything from `CONFIG`.
- **You normally only edit two things per client:** (1) the `<title>` + `<meta
  description>` in `<head>` (for Google), and (2) the `CONFIG = {}` object.
- `CONFIG` fields: `business, tagline, subtagline, phone, phoneRaw, email, address,
  primary/accent/dark` (colors), `hours` (per-day; `""` = Closed), `about`, `services[]`
  (icon/title/desc), `reviews[]` (text/name), `gallery[]` (image URLs; `[]` hides it),
  `mapEmbed` (`""` hides it), `facebook`, `instagram`.
- The render script at the bottom (`(function(){...})()`) reads CONFIG and injects HTML.
  Leaving optional sections empty auto-hides them.
- No dependencies — opens directly in a browser. Host by drag-drop to Netlify Drop or
  via GitHub Pages.

---

## 5. Next steps / open offers (where to resume)

At the end of round 2, Claude offered these and the user has **not yet chosen**. Good
candidates to pick up:

1. **More industry example sites** — e.g. a salon/barbershop and a landscaper/trades
   variant, so the demo set covers the user's top target industries. (Clone
   `template/index.html`, swap the `CONFIG` + head tags, validate the JS.)
2. **A working contact form** — wire up a free option (Formspree or Netlify Forms) so
   the "Contact" section actually emails the business owner. Currently the template
   shows contact info but has no submit-able form.
3. **A personal portfolio / landing page for Charlie** — a one-pager listing his demo
   sites + his pitch, so when an owner asks "who are you?" he can text one link. This
   directly supports the "trust/who-are-you" objection in the playbook.

Other natural extensions not yet offered:
- A printable one-page flyer/leaflet to leave at businesses.
- A simple written service-agreement template (scope + price + pay-on-delivery) to
  back up the playbook's "paper trail" advice.
- More industry-specific `CONFIG` presets (church, vet, nail salon, etc.) matching the
  user's original target list.

---

## 6. Useful context / conventions for the new session

- **Repo scope:** GitHub tools are restricted to `charliegillet/0531momidea`.
- **Branching rule:** Develop and push to `claude/small-business-outreach-ideas-gW6fV`.
  Never push to a different branch without explicit permission. Don't open a PR unless
  the user asks.
- **Validation habit:** When editing template HTML, validate the `CONFIG` block is
  valid JS before committing, e.g.:
  ```
  node -e "const fs=require('fs');const s=fs.readFileSync('template/FILE.html','utf8');const m=s.match(/const CONFIG = (\{[\s\S]*?\n\});/);eval('('+m[1]+')');console.log('OK')"
  ```
- **User's original target list (for reference):** small restaurants, churches, car
  washes, mechanics/gas stations, laundromats, dry cleaners, nail salons, tutoring,
  music lessons, education/community colleges, care homes, vets, food banks,
  drop shipping, funeral homes, farmers markets/nurseries. (Expanded list lives in the
  playbook.)
- **Environment note:** This runs in an ephemeral remote container — anything not
  committed + pushed is lost. Always commit and push deliverables.

---

*End of handoff. New session: read the files in §3, then continue from §5.*
