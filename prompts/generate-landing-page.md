# Generate The Human-Readable Landing Page

Produce a polished, self-contained HTML landing page — the public **human-readable surface** of this Engagement Stack — from the canonical Career OS data. It should look like a modern, recruiter-ready personal site: navy-themed, a single file, no external dependencies.

This reproduces the kind of page demonstrated by the reference instance at **https://mikebengtson.github.io/**.

> Engagement Stack's default human surface is the GitHub-rendered Markdown (README + folder READMEs). This landing page is an **optional, higher-polish** surface for people who want a designed site in front of the same canonical facts. The page is the human door; `AGENTS.md` is the machine door.

## Use the template — don't redesign

Start from [`../submissions/web/landing-page.template.html`](../submissions/web/landing-page.template.html). It carries the full navy theme and every section pre-built, with `{{PLACEHOLDER}}` tokens and HTML comments mapping each region to its Career OS source. **Fill the placeholders; keep the CSS, tokens, and structure intact.** Repeating regions (experience items, skill pills, repo cards, stat items) include a commented example block to clone per record.

## Read these canonical files first (do NOT invent facts)

- `profile/identity.md` + `.yaml` — full name, professional label/title, location + remote posture, public links (LinkedIn, GitHub, email, and phone only if the user publishes it).
- `profile/positioning.md` — one-line positioning + short bio.
- `cv/work-history.md` + `.yaml` — roles, dates, scope, outcomes → the **Experience** timeline.
- `cv/skills.md` + `.yaml` — skills/competencies → the **Skills** section.
- `evidence/` (especially `evidence/recent-repos.md`, `evidence/github.md`, `evidence/live-products.md`) and `portfolio/` — public repos and live products → the **Open Source / Proof** cards.
- `engagements/current-preferences.md` — availability, engagement types, location/work-type posture → the hero availability badge + **Availability** section. **Public-safe fields only.**
- Signature metrics from `profile/` / `cv/` / `portfolio/` → the **Stat band**.

## Sections to populate (the template has all of these)

1. **Sticky nav** — brandmark (name + short role); section anchors; and three CTAs: **Résumé** (→ the rendered résumé PDF), **🤖 Agents** (→ this repo's `AGENTS.md` blob URL, e.g. `https://github.com/<user>/<repo>/blob/main/AGENTS.md`), and **Contact** (mailto).
2. **Hero** — availability badge (e.g. "Available <Month Year> · <engagement types>"), name, title, one-line positioning, location + remote posture, and a contact row: email, phone (if public), LinkedIn, GitHub, the gold **Download Résumé** button, and the cyan **🤖 Agents** button → `AGENTS.md`.
3. **Stat band** — 3–4 signature, public-safe outcomes (big number + label).
4. **Experience** — reverse-chronological; feature the recent roles, taper older ones. Use the same wording discipline as the résumés (quantified outcomes; phrase targets as targets, not delivered results).
5. **Skills / Competencies** — grouped skill pills.
6. **Open Source / Proof** — a card per public repo (name, description, primary language, link) from `evidence/`.
7. **Availability** — engagement types sought + location/work posture + an email/résumé CTA. **No compensation, rates, or private constraints.**
8. **Footer** — name, links, one line.

## Rules

- **Self-contained:** inline all CSS in one `<style>` block; no external CSS/JS/fonts/network requests; system font stack only.
- **Public-safe:** never include compensation, rates, negotiation, or anything from a `private/` overlay. If the user maintains private overlays, the page must not reveal that data — only `AGENTS.md` + the public files feed it.
- **Don't invent facts:** every claim traces to a canonical file. Flag missing fields as `[gap]` and ask.
- **Keep both the Résumé and 🤖 Agents CTAs** in the nav *and* the hero — they are part of the design contract.
- Keep the navy theme: accent `#1f3d5c`, the **gold** résumé CTA, the **cyan** Agents CTA. Match [`../styles/navy.css`](../styles/navy.css) tokens.

## Output & deploy

- Write the page to **`docs/index.html`** (self-contained) and create an empty **`docs/.nojekyll`**.
- Copy the rendered résumé PDF next to it (e.g. `docs/<name>-resume.pdf`) so the Résumé CTA resolves, or point the CTA at wherever the PDF is published.
- Deploy via **GitHub Pages**: either Settings → Pages → *Branch: main, folder: `/docs`*, or copy `docs/index.html` (+ the PDF) into a `<username>.github.io` user-site repo. (Pages from a **private** repo needs a paid plan; a public user-site repo works on the free plan.)

## Result

Report the output path, the sections you populated, any `[gap]` fields, and the one-line deploy instruction. Confirm the résumé-PDF and `AGENTS.md` links resolve.
