# Web Landing-Page Adapter

This adapter produces the **human-readable landing page** — the optional, higher-polish public surface of an Engagement Stack. It's a single, self-contained navy-themed HTML page that puts a designed site in front of the same canonical Career OS facts.

> Engagement Stack's default human surface is the GitHub-rendered Markdown (root `README.md` + folder READMEs). This landing page is an **optional** upgrade for people who want a recruiter-ready personal site. The page is the human door; `AGENTS.md` is the machine door.

## What's in here

- [`landing-page.template.html`](landing-page.template.html) — the proven navy theme and every section pre-built, carrying `{{PLACEHOLDER}}` tokens and HTML comments that map each region to its Career OS source. Repeating regions (experience items, skill pills, repo cards, stat items, availability cards) ship with a commented example block to clone per record.
- Pairs with the generator prompt: [`../../prompts/generate-landing-page.md`](../../prompts/generate-landing-page.md).

## How it works

1. Run the prompt `prompts/generate-landing-page.md` against your Career OS.
2. The prompt reads the canonical files (`profile/`, `cv/`, `evidence/`, `portfolio/`, `engagements/`) and **fills the template** — it does **not** redesign it. Keep the CSS, brand tokens, and structure intact.
3. Output the filled page to `docs/index.html` and deploy via GitHub Pages.

**Design contract (do not drop):** navy accent `#1f3d5c`; the **gold** Résumé CTA (`.cta-resume` / `.contact-btn.resume`) and the **cyan** 🤖 Agents CTA (`.cta-agents` / `.contact-btn.agents`), each present in **both** the nav and the hero. Matches the `styles/navy.css` résumé tokens.

**Public-safe:** inline CSS only, system fonts, no external/network requests. Never include compensation, rates, negotiation, or anything from a `private/` overlay. Every claim must trace to a canonical file; flag missing fields as `[gap]`.

## Placeholders

Identity / hero
- `{{FULL_NAME}}`, `{{FIRST_NAME}}`, `{{INITIALS}}` (favicon + brandmark chip)
- `{{SHORT_ROLE}}` (brandmark), `{{TITLE}}` (hero/footer label)
- `{{POSITIONING}}` (one-liner; bold a phrase with `<b>`), `{{LOCATION}}`, `{{LOCATION_SHORT}}`
- `{{AVAILABILITY_BADGE}}` (e.g. "Available <Month Year> · <engagement types>")
- `{{CANONICAL_URL}}` (og/canonical, e.g. `https://<user>.github.io/engagement-stack/`)

Contact / CTAs
- `{{EMAIL}}` (used in `mailto:` + visible label)
- `{{PHONE}}` (used in `tel:` + visible label) — **include only if the user publishes a phone number; otherwise delete those buttons**
- `{{LINKEDIN_URL}}` + `{{LINKEDIN_LABEL}}`, `{{GITHUB_URL}}` + `{{GITHUB_LABEL}}`
- `{{RESUME_PDF}}` (rendered résumé PDF), `{{RESUME_HINT}}` (e.g. "PDF · 3 pages")
- `{{AGENTS_URL}}` → this repo's `AGENTS.md` blob, form `https://github.com/<user>/<repo>/blob/main/AGENTS.md`

About
- `{{ABOUT_TITLE}}`, `{{ABOUT_LEDE}}`, `{{ABOUT_PARAGRAPH_1}}`, `{{ABOUT_PARAGRAPH_2}}`

Stat band (3–4)
- `{{STAT_1_NUMBER}}`…`{{STAT_4_NUMBER}}` and `{{STAT_1_LABEL}}`…`{{STAT_4_LABEL}}`

Experience (clone the `<!-- EXPERIENCE ITEM -->` blocks)
- `{{EXP_COMPANY}}`, `{{EXP_DATES}}`, `{{EXP_CONTEXT}}`
- featured roles: `{{ROLE_TITLE}}`, `{{ROLE_SPAN}}`, `{{ROLE_SUMMARY}}`, `{{ROLE_BULLET_*}}`
- normal items: `{{EXP_BULLET_*}}`; optional `earlier` card: `{{EARLIER_*}}`

Skills (clone the `<!-- SKILL PILL -->` / competency group)
- `{{SKILL_GROUP_TITLE}}`, `{{SKILL}}`

Open source / proof (clone the `<!-- REPO CARD -->` blocks)
- featured (optional): `{{FEATURED_REPO_NAME}}`, `{{FEATURED_REPO_BADGE}}`, `{{FEATURED_REPO_LANG}}`, `{{FEATURED_REPO_DESC}}`, `{{FEATURED_STAT_*_V}}` / `{{FEATURED_STAT_*_K}}`, `{{FEATURED_REPO_URL}}`, `{{FEATURED_LIVE_URL}}`
- cards: `{{REPO_NAME}}`, `{{REPO_DESC}}`, `{{REPO_LANG}}`, `{{REPO_URL}}`, `{{REPO_META_1}}`, `{{REPO_META_2}}`
- `{{STATS_DATE}}`, `{{REPO_NOTE}}` (measurement methodology)

Availability / footer
- `{{AVAILABILITY_LEDE}}`; per card: `{{AVAIL_CARD_TITLE}}`, `{{AVAIL_CARD_BODY}}`, `{{AVAIL_CARD_TAG}}`
- `{{YEAR}}`, `{{ENGAGEMENT_STACK_URL}}`

## Deploy (GitHub Pages)

- Write the filled page to **`docs/index.html`** and add an empty **`docs/.nojekyll`**. Copy the résumé PDF next to it (e.g. `docs/<name>-resume.pdf`) so the Résumé CTA resolves, or point `{{RESUME_PDF}}` at wherever the PDF lives.
- Then either:
  - **Settings → Pages → Branch: `main`, folder: `/docs`** on a **public** repo, or
  - copy `docs/index.html` (+ the PDF) into a **`<username>.github.io`** user-site repo.
- Pages from a **private** repo requires a **paid** plan. A public user-site repo works on the free plan.

After deploy, confirm the résumé-PDF and `AGENTS.md` links resolve.
