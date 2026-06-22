# Operation: Spartans Never Die — Halo LAN Party Site

A single-file static site for a Halo MCC LAN party. No build step, no dependencies.
Mobile-first, Halo × Tron themed. Current party: **Friday, June 26, 2026 · 6:30 PM MT**.

## Deploy to GitHub Pages

1. Create a new GitHub repo (e.g. `halo-lan-party`).
2. Drop `index.html` **and the `assets/` folder** in the root. Structure should look like:
   ```
   /
     index.html
     assets/
       spartan.jpg
   ```
3. **Repo → Settings → Pages** → Source: **Deploy from a branch** → Branch: **main** / **(root)** → Save.
4. Wait ~1 minute. Site lives at `https://<your-username>.github.io/halo-lan-party/`.

If you want a custom domain or `username.github.io` style URL instead, name the repo `<your-username>.github.io` and it'll serve at the root.

## Editing

Everything is in `index.html` — HTML structure at the top of `<body>`, CSS in the `<style>` block, countdown JS at the bottom.

Common tweaks:

| What | Where |
|---|---|
| Date / time | `target` variable in the `<script>` block, plus the `.hero__chips` and `.card-title`/`.sched-time` text in the HERO + BRIEFING sections |
| Countdown | Segmented cells (`#cd-days`/`#cd-hours`/`#cd-mins`/`#cd-secs`); the JS auto-fills them from `target` |
| Discord invite URL | `href` on the `.discord-cta` link (search for `discord.gg/`) |
| Gamertags | `.roster-tag` divs in the ROSTER section |
| Schedule items | `.sched-item` blocks in the BRIEFING section |
| Mission code stamp | `.stamp` span in the HERO section |
| Hero image | Replace `assets/spartan.jpg` with a wide (~2:1) landscape JPG/PNG; it's used full-bleed via `object-fit: cover`. Tune framing with `object-position` on `.hero__img` |

## Layout notes

- **Mobile-first CSS.** Base styles target phones; `min-width` media queries (560 / 760 / 1000px) scale up. Test narrow first.
- Full-bleed hero uses `svh` units (not `vh`) so mobile browser chrome doesn't hide content. Keep it that way.
- `body` has `overflow-x: hidden` as a guard; avoid `100vw` widths (they cause sideways scroll). Decorative motion is disabled under `prefers-reduced-motion`.

## Local preview

It's a static file — open `index.html` directly, or serve the folder: `python -m http.server 5599` then visit `http://localhost:5599`. (`.claude/launch.json` defines this for the Claude Code preview panel.)

## Fonts

Google Fonts: Saira Stencil One (display), Orbitron (countdown / tech numerals), Rajdhani (body), Share Tech Mono (HUD readouts). Loaded via CDN — no install needed.
