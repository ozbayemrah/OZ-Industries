# CLAUDE.md

**OZ Industries GmbH** (in formation): website + 4-slide R&D briefing deck for an aerospace R&D venture in Graz (human–machine systems for in-orbit servicing). Successor of the old `XUX/` site (working name "XUX Studio"; that folder no longer exists).

## Structure
- `index.html`, `work-system.html`: static pages, inline CSS/JS, no build step. Both share the same `:root` tokens, so keep them in sync.
- `index.html` sections: hero with a live canvas "MONOLITH predictive view" concept simulation (latency slider), 01 Problem, 02 System (chain diagram + pillar tabs), 03 Two-engine model, 04 Roadmap (3 phases + 12-month Gantt, bars placed from `data-s`/`data-e`), 05 Ecosystem (status: Active / Applying / Target), 06 Founder + CTAs.
- `assets/vcard.js`: single source for contact data (`CONTACT` object) → QR codes + "Save contact" links on both pages. Never edit the QR itself.
- `assets/viz.js`: HUD-wireframe NASA 3D models in the deck; colours from `--viz-*` CSS vars per theme.
- Everything self-hosted (`assets/fonts`, `assets/vendor` three.js r128 + GLTF/Draco loaders + qrcode-generator). No CDNs, so it keeps working offline.

## Design ("MONOLITH grid", since 2026-11-16)
- Swiss 12-column grid, **dark theme primary** (`#0B0E14` / `#F4F6F8`), cyan `#00E5FF` = signal, amber `#FF9100` = warning/latency. Light theme optional; uses darker `--cyan-ink` / `--amber-ink` for text contrast. Theme shares the `theme` localStorage key with the portfolio (dark unless `"light"` is stored).
- Space Grotesk (sentence-case headings, weight 500) + JetBrains Mono (labels, data). Reference tone: Anduril / Linear / ESA docs. Avoid sci-fi clichés (no grain, no ticker, no hazard stripes).
- Deck: no auto-advance, minimal text, no founder slide (deliberate). Must fit without scrolling from iPad portrait up (checked 768×1024 → 1920×1080); phones scroll inside a slide.

## Content rules
- Audience: aws evaluators, Science Park Graz / ESA BIC jury, co-founders, B2B clients. User wants it **lean**: show skill, don't over-detail.
- Claims are phrased as goals/plans. No absolute claims ("zero-error", "world's first", "fully compliant"). Partner/programme rows carry honest statuses: only FH JOANNEUM is "Active"; aws + Science Park/ESA BIC are "Applying"; the rest are "Target".
- Real companies (e.g. propulsion makers) are **not named** as integration partners without an agreement; say "Austrian propulsion platforms".
- Brand: logo `OZ.` + "Industries" tag. Name is **OZ Industries** (not "OZ Industry"). "GmbH in formation" strip + footer "(in formation)" stay until the Firmenbuch entry.
- Contact: FH mail + LinkedIn + vCard. Don't publish oz.industries / office@oz.industries until the domain and mailbox are live; then update `website` in `assets/vcard.js` and add a `CNAME`.

## What is public vs. confidential (this repo is public)
- **Public since 2026-11-16 (user decision):** MONOLITH (software/HMI framework + cockpit), REMORA (docking claw), OCTOPUS (servicing micro-crawler).
- **Still confidential:** the names and technical specifics of the future R&D pipeline items. The site only says "adaptive compliant toolheads" and "zero-power surface grip". Don't add their internal names, materials or mechanisms. Same for anything else in the strategy documents in the parent `AAA Start-up/` folder that isn't on the site.

## Testing / hosting
- Serve over `http://` (`python -m http.server`); GLB models fail on `file://`.
- GitHub Pages from `main` (`ozbayemrah/OZ-Industries`, recreated 2026-11-16; URL is case-sensitive: ozbayemrah.github.io/OZ-Industries/).
