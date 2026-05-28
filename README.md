# Operation: Family Reunion — Halo LAN Party Site

A single-file static site for a Halo MCC LAN party. No build step, no dependencies.

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
| Date / time | `target` variable in the `<script>` block, plus the `hero-data` div in the HERO section |
| Discord invite URL | `href` on the `.discord-cta` link (search for `discord.gg/`) |
| Gamertags | `.roster-tag` divs in the ROSTER section |
| Schedule items | `.schedule-item` blocks in the BRIEFING section |
| Mission code stamp | `.mission-stamp` div in the HERO section |
| Hero image | Replace `assets/spartan.jpg` with any same-ish-aspect-ratio JPG/PNG |

## Fonts

Google Fonts: Saira Stencil One (display), Rajdhani (body), Share Tech Mono (HUD readouts). Loaded via CDN — no install needed.
