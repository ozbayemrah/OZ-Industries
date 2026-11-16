# CLAUDE.md

**OZ Industries GmbH** (in formation): website + 4-slide R&D briefing deck for an aerospace R&D venture in Graz (human–machine systems for in-orbit servicing). Successor of the old `XUX/` site (working name "XUX Studio"; that folder no longer exists).

## Structure
- `index.html`, `work-system.html`: static pages, inline CSS/JS, no build step. Both share the same `:root` tokens, so keep them in sync.
- **The deck (`work-system.html`) is hidden since 2026-11-16 (user decision):** no links to it from the site, `noindex` meta. It's still reachable by direct URL. Re-link it (header button + footer) only when the user asks.
- `index.html` sections: hero with a canvas "MONOLITH · Mission view" concept simulation — a full looped servicing run (approach → spin sync → gecko-pad capture → detumble → OCTOPUS crawl → unjam → panel B deploys, ~44 s), camera zooms in for the close work, phase strip + status line + readouts, latency slider and Replay button; every frame is a pure function of mission time `t` (timeline in the `PH` array). 01 Problem, 02 System (chain diagram + pillar tabs) with 02.1 "Capture & hold" (`#grip`, 4-step gecko-grip SVG sequence + design-goal strip), 03 Two-engine model, 04 Roadmap (3 phases + 12-month Gantt, bars placed from `data-s`/`data-e`), 05 Ecosystem (status: Active / Applying / Target), 06 Founder + CTAs.
- `assets/vcard.js`: single source for contact data (`CONTACT` object) → QR codes + "Save contact" links on both pages. Never edit the QR itself.
- `assets/viz.js`: HUD-wireframe NASA 3D models in the deck; colours from `--viz-*` CSS vars per theme.
- Everything self-hosted (`assets/fonts`, `assets/vendor` three.js r128 + GLTF/Draco loaders + qrcode-generator). No CDNs, so it keeps working offline.

## Design ("MONOLITH grid", since 2026-11-16)
- Swiss 12-column grid, **dark only** (`#0B0E14` / `#F4F6F8`), cyan `#00E5FF` = signal, amber `#FF9100` = warning/latency. The light theme and its toggle were removed on 2026-11-16 (user decision); don't add them back.
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
- **Public since 2026-11-16 (user asked for it):** the gecko-grip *idea* — gecko-inspired dry adhesion on REMORA's capture pads (microwedges, van der Waals, shear-loaded lock, peel release, 0 W hold). Mechanism level only; no specific materials (e.g. nanotube arrays) or numbers.
- **Still confidential:** the origami / folding-toolhead track (site says only "adaptive compliant toolheads") and other pipeline specifics. Don't add its internal name, materials or mechanism. Same for anything else in the strategy documents in the parent `AAA Start-up/` folder that isn't on the site.

## Testing / hosting
- Serve over `http://` (`python -m http.server`); GLB models fail on `file://`.
- GitHub Pages from `main` (`ozbayemrah/OZ-Industries`, recreated 2026-11-16; URL is case-sensitive: ozbayemrah.github.io/OZ-Industries/).
