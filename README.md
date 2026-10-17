# OZ Industries — website

One-page site and partner-briefing deck for **OZ Industries GmbH** (in formation): human-factors and interface design for space and extreme environments, Graz, Styria, Austria.

- `index.html` — main site (hero + vCard QR, problem, services, method, research, founder, roadmap, contact).
- `work-system.html` — 4-slide partner briefing. Arrow keys / space / swipe to navigate, `F` for fullscreen, `#3` in the URL opens slide 3.
- `assets/vcard.js` — the shared contact card. Edit the `CONTACT` object there; every QR code and "Save contact" link on both pages regenerates from it.

No build step, no CDN — fonts, three.js, Draco and the QR library are all self-hosted, so the site works offline. Serve locally with `python -m http.server` (the 3D models need `http://`, not `file://`).

Hosted on GitHub Pages from `main`: https://ozbayemrah.github.io/oz-industries/

The GmbH is not registered yet. The "GmbH in formation" banner and the "(in formation)" footer note are deliberate — remove them once the Firmenbuch entry exists.
