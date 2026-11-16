# OZ Industries — website

Website and R&D briefing deck for **OZ Industries GmbH** (in formation): human–machine systems for in-orbit servicing and modular space robotics. R&D in Graz, Styria, Austria.

- `index.html`: main site (hero with a live latency-compensation concept simulation, problem, system, model, roadmap, ecosystem, founder).
- `work-system.html`: 4-slide R&D briefing. Use arrow keys, space or swipe to navigate, and `F` for fullscreen. `#3` in the URL opens slide 3.
- `assets/vcard.js`: the shared contact card. Edit the `CONTACT` object there; every QR code and "Save contact" link on both pages regenerates from it.

No build step, no CDN: fonts, three.js, Draco and the QR library are all self-hosted, so the site works offline. Serve locally with `python -m http.server` (the 3D models need `http://`, not `file://`).

Hosted on GitHub Pages from `main`: https://ozbayemrah.github.io/oz-industries/

The GmbH is not registered yet. The "GmbH in formation" strip and the "(in formation)" footer note are deliberate; remove them once the Firmenbuch entry exists.
