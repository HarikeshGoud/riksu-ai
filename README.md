# riksu.ai — launch poster page

`index.html` is a **single-viewport poster** for riksu.ai — no scrolling, everything on
one screen. It's a temporary placeholder to put on the domain while the full website
(in development on `localhost:3020`) gets finished. No build step, no dependencies —
all CSS/JS inline; fonts load from Google Fonts (Instrument Serif, Inter, JetBrains Mono).

**What's on it:** logo · "full site — launching soon" stamp · headline ("We build AI
systems that work while you sleep.") · one-line pitch · services ticker (chatbots, voice
agents, dashboards, workflow automation, internal tools, AI strategy) · "Book a Free
15-min AI Audit" mailto button · direct emails · live Hyderabad clock.

**Motion:** staggered headline reveal, self-drawing underline, breathing glow, ambient
aurora blobs (periwinkle/violet/deep-blue, wander + rotate + breathe), drifting smoke,
looping services marquee (pauses on hover), cursor-follow light, pulsing dot, grain.
In light mode the giant "riksu" outline uses the theme's darkest ink for presence. Respects `prefers-reduced-motion`. Fits one screen from phones (375×667) to
desktop; short-window fallbacks at `max-height: 620px`.

**Theme:** blue Foundations palette (#3D52A0 · #7091E6 · #8697C4 · #ADBBDA · #EDE8F5)
with **auto dark/light**: follows the device's `prefers-color-scheme`, plus a round
☾/☀ toggle button in the top bar that overrides it (saved in localStorage, smooth
cross-fade). Light = pale lavender + navy ink; dark = near-black navy + lavender text.
`?theme=dark|light` forces one (handy for screenshots). To go back to the original
orange: `cp poster-orange.html index.html`, then re-sync the preview copy.

Other files:
- `poster-orange.html` — the poster in the original dark orange/espresso theme.
- `poster-blue-dark.html` — dark-blue-only snapshot (pre-toggle), kept as reference.
- `onepager-backup.html` — the earlier full one-page site build (hero → services →
  pricing → FAQ → contact); reference only, not meant to deploy.

## Preview locally

From a Claude Code session in the `fasttracks reciepts` project, the preview config
`riksu-landing` (`.claude/launch.json`) serves this folder on **http://localhost:3025**.

> Note: the preview helper can't read `~/Documents` (macOS privacy/TCC), so the config
> serves a synced copy at `/Users/Shared/riksu-ai-preview`. After editing `index.html`,
> re-sync with:
> `rsync -a --delete ~/Documents/riksu-ai/ /Users/Shared/riksu-ai-preview/`

Or just open `index.html` directly in a browser.

## Deploy (pick one)

- **Cloudflare Pages / Netlify** — drag-and-drop this folder in their dashboard, then
  point the `riksu.ai` DNS at it. Fastest path to live.
- **Azure Static Web Apps** — same flow as the Fasttracks sites: push this folder to a
  GitHub repo, create a SWA, add the custom domain.
- **GitHub Pages** — push, enable Pages, add `riksu.ai` as custom domain (CNAME).

Contact is fully static: the button opens the visitor's email app pre-filled to
harikesh@riksu.co (cc sushruta@riksu.co). No backend needed.

## Before going live

- [ ] Confirm the two emails work (`harikesh@riksu.co`, `sushruta@riksu.co`).
- [ ] Optional: add an `og:image` for link previews on WhatsApp/LinkedIn.

## Screenshot / capture mode

Append `?static=1` to land all animations on their end state (useful for automated
screenshots). The page never scrolls, so captures at the top are always complete.
