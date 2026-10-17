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

## Brand architecture (from `../OZ_Brand_Strategy_Report.pdf`, adapted)
- Company name stays **OZ Industries** (user decision 2026-10-17). The report says "OZ Systems GmbH" — do not adopt that.
- **Operation Zenith** = engineering principle, named in the Method section (SEC-03).
- **MONOLITH Framework** = the product: numbered design rules (M1, in research) + component kit (M2) + review method (M3), both planned 2027. Own section `#monolith` (SEC-05); also named in the Level 03 Assurance tile, the roadmap, and the deck's slide 3 label.
- Not used on purpose: the O/Z acronym ("Zero-error interaction"), the Green KAIT energy claims, and "Remora". Keep absolute claims ("zero-error", "fully compliant") off the public site.
