# riksu.ai — launch poster (ai.riksu.co)

Read this before touching anything.

## What this is

A **single-viewport, no-scroll animated poster** for riksu.ai — Harikesh & Sushruta's
AI automation agency (Hyderabad, clients worldwide). It's a temporary placeholder on
`ai.riksu.co` while the full website is designed separately by Harikesh (different
project, not in this repo). Keep this page a poster: **one screen, zero scrolling**
(`100svh` + `overflow:hidden`), everything must fit from a 375×667 phone to desktop
(there are `max-height:620px` fallbacks — preserve them).

**riksu.ai is a separate venture from Fasttracks Car Care.** Fasttracks is riksu's
flagship *client* (case study). Never mix Fasttracks infrastructure, repos, or branding
into this project.

## Files

| File | What it is |
|---|---|
| `index.html` | THE site. Fully self-contained (inline CSS/JS, Google Fonts only external). |
| `CNAME` | `ai.riksu.co` — GitHub Pages custom domain. **Never delete.** |
| `.nojekyll` | Keeps Pages from running Jekyll. Keep. |
| `poster-orange.html` | Snapshot: original dark orange/espresso theme. Reference/revert only. |
| `poster-blue-dark.html` | Snapshot: dark-blue-only version (pre theme-toggle). Reference only. |
| `onepager-backup.html` | Old scrolling one-pager (hero→pricing→FAQ→contact). **Never deploy/link.** |

## Design system

- Palette (from a Shopify-Foundations reference the founders chose):
  `#3D52A0 · #7091E6 · #8697C4 · #ADBBDA · #EDE8F5`
  Light mode: bg `#eceaf6`, ink `#212950`. Dark mode: bg `#0b0e1c`, text `#ede8f5`.
- Fonts: **Instrument Serif** (display + italic accents), **Inter** (body),
  **JetBrains Mono** (letterspaced uppercase labels/stamps).
- Signature elements: giant outlined bg word "riksu", rotated pill stamps, hand-drawn
  underline squiggle on *sleep.*, services marquee ticker, ambient aurora blobs,
  grain overlay, cursor-follow glow, live Hyderabad clock (IST).
- **Quirk:** CSS accent vars are named `--orange`/`--orange-bright`/`--orange-deep`
  but hold BLUE values (kept for painless diffs against the orange snapshot). Don't
  "fix" the names.
- Theming: follows device `prefers-color-scheme`; ☾/☀ button sets `data-theme` on
  `<html>` + localStorage key `riksu-theme` (manual choice beats system). All colors
  flow through vars — new colors must too, defined for BOTH themes.
- URL params: `?theme=dark|light` forces a theme; `?static=1` lands all animations on
  end state (both exist for automated screenshots — keep them working).
- Respect `prefers-reduced-motion` for any new animation.

## Content facts (for copy changes)

- Headline: "We build AI systems that work while you sleep."
- Services: AI Chatbots & Agents · AI Voice Agents · Smart Dashboards · Workflow
  Automation · Internal Tools & CRMs · AI Strategy & Audits.
- Funnel: **free 15-minute AI audit** (mailto button — no backend, keep it static).
- Emails: harikesh@riksu.co · sushruta@riksu.co (domain is riksu.**co**; brand is riksu.ai).
- Tone: confident, a little playful, anti-corporate ("Built with AI, powered by humans").

## Deploy

- **Hosting:** GitHub Pages, repo `HarikeshGoud/riksu-ai` (Harikesh's PERSONAL account,
  not the Fasttracks org account harikesh-ft). Repo must stay **public** (free Pages).
- **Pipeline:** push to `main` → Pages rebuilds → live in ~1 minute. No CI files needed.
- **Domain:** `ai.riksu.co` → CNAME record in **Cloudflare** (riksu.co zone) pointing to
  `harikeshgoud.github.io`, **DNS only / grey cloud** (GitHub can't issue its TLS cert
  behind Cloudflare's proxy).
- To push you must be authenticated as HarikeshGoud: `gh auth login` (device flow).
- Commits: author "Harikesh <harikeshgoud@gmail.com>".

## Status as of 2026-07-15

- [x] Poster built (blue palette, auto dark/light + toggle, aurora, ticker, clock)
- [x] Repo created + pushed; Pages enabled, build green, cname set
- [ ] **Cloudflare CNAME record `ai` → `harikeshgoud.github.io` (DNS only)** — Harikesh
      to add in dash.cloudflare.com
- [ ] After DNS resolves + GitHub issues the cert: enforce HTTPS —
      `gh api -X PUT repos/HarikeshGoud/riksu-ai/pages -f cname=ai.riksu.co -F https_enforced=true`
- [ ] Optional: `og:image` for WhatsApp/LinkedIn link previews
- [ ] Someday: replace poster with the full site (Harikesh's separate build)
