# Raja Ampat kiosk — ZOO Sea World Prague

A touchscreen application running beside our Raja Ampat tank at ZOO Mořský svět (Sea World Prague), the Czech Republic's only public marine aquarium. **This was the first of the four kiosks and it is the reference implementation** — the design system every later application inherited was worked out here.

**Live:** https://velenskym.github.io/Morskysvet-kiosk/
**Try it in a simulated kiosk screen:** https://velenskym.github.io/morskysvet-euac/

Plain HTML, CSS and JavaScript. No framework, no build step, no server. Hosted free on GitHub Pages, displayed by Chromium in kiosk mode on a small Linux box next to the glass.

---

## Pages

| File | What it is |
|---|---|
| `index.html` | Home — hero and three cards |
| `raja-ampat.html` | Raja Ampat and the Coral Triangle: why this is the most biodiverse place in the ocean |
| `utes.html` | The coral reef: how it forms, how it works, what threatens it |
| `zivocichove.html` | A guide to the animals in the tank — sidebar list, detail panel with photograph, names, facts and distribution map |
| `admin.html` | Content editor (not yet wired to the GitHub API on this tablet — the working version is in [Morskysvet-GBR](https://github.com/velenskym/Morskysvet-GBR)) |

Both languages live in the same files: every text node carries `data-cs` and `data-en` attributes and one function swaps them.

## What was settled here

If you are looking for the origin of the patterns used across all four kiosks, they are in this repository:

- One fixed design resolution (1920×1080) scaled with CSS to the panel, instead of responsive CSS.
- A type scale for a standing visitor at arm's length — body text **never below 21 px** at the design width.
- The three-minute inactivity reset that returns the screen to the home page, so the next visitor always starts from a clean state.
- Drag-scroll for both mouse and touch: visitors do not look for scrollbars.
- Bilingual content by attribute rather than by duplicated pages.

This tablet has no video; that pattern came later with the octopus and the reef bleaching page.

## Built for one specific screen

**Opening `index.html` on a laptop or a phone will not look right** — the layout assumes the kiosk panel. To see it as a visitor does, use the [kiosk simulator](https://velenskym.github.io/morskysvet-euac/), which frames the app at its native resolution and scales the whole frame to fit your screen.

## Running it locally

```bash
git clone https://github.com/velenskym/Morskysvet-kiosk.git
cd Morskysvet-kiosk
python3 -m http.server 8000
```

Then open http://localhost:8000 in a browser window sized to 1366×768 (in Chrome: DevTools → device toolbar → set a custom 1366×768 device).

## Reusing this for your own institution

You are welcome to. The code is MIT-licensed; the photographs and texts are not — see [LICENSE](LICENSE).

- **The machine underneath it** — Lubuntu with Openbox, autologin, Chromium kiosk flags, a watchdog and automatic power-off at closing time — is documented in [KIOSK-SETUP.md](https://github.com/velenskym/morskysvet-euac/blob/main/KIOSK-SETUP.md).
- The three sister applications: [jellyfish](https://github.com/velenskym/Morskysvet-meduzy), [octopus](https://github.com/velenskym/Morskysvet-chobotnice), [Great Barrier Reef](https://github.com/velenskym/Morskysvet-GBR).

## Known gaps

The species guide still needs complete data and photographs for every animal in the tank, and the admin panel here has not been connected to the GitHub API yet.

## Contact

Mikuláš Velenský — Curator, ZOO Sea World Prague
velenskym@gmail.com · [morskysvet.cz](https://www.morskysvet.cz) · [github.com/velenskym](https://github.com/velenskym)

Shared with the EUAC community. If you build something from this, I would like to hear about it.
