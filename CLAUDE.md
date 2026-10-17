# CLAUDE.md

**OZ Industries GmbH** start-up site + 4-slide partner deck. Active successor of `../XUX/` (old working name "XUX Studio"), copied over and rebranded 2026-10-17. Do new work here, not in `XUX/`.

## Structure
- `index.html`, `work-system.html` — static pages, inline CSS/JS, no build step. Both share the same `:root` tokens; keep them in sync.
- `assets/vcard.js` — single source for contact data (`CONTACT` object) → QR codes + "Save contact" links on both pages. Never edit the QR itself.
- `assets/viz.js` — grey HUD-wireframe NASA 3D models (ISS, TDRS, EVA suit, helmet) in the deck; colours from `--viz-*` CSS vars per theme.
- Everything self-hosted (`assets/fonts`, `assets/vendor` three.js r128 + GLTF/Draco loaders + qrcode-generator). No CDNs — keep it working offline.

## Conventions
- Styled on the `design/` portfolio system: JetBrains Mono + Space Grotesk, `--hazard` red accent, stripe buttons, corner brackets, ticker. Light theme is default; theme shares the `theme` localStorage key with the portfolio.
- Brand: logo `OZ.` + "Industries" tag. Company not registered yet → "GmbH in formation" banner (`.wip`) + footer "(in formation)" stay until the Firmenbuch entry; then remove both.
- Deck: no auto-advance, minimal text, no founder slide (deliberate). Must fit without scrolling incl. iPad portrait/landscape.
- Claims are phrased as goals, not facts.
- Serve over `http://` to test (`python -m http.server`); GLB models fail on `file://`.
- Hosting: GitHub Pages from `main` (`ozbayemrah/oz-industries`). Custom domain planned later; when added, update `website` in `assets/vcard.js`.
