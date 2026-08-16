# STARWANDER — an interactive 3D cosmos

A fun, mobile-friendly WebGL experience built with [Three.js](https://threejs.org). Drift through a living galaxy — a banded gas giant with rings, moons, an asteroid belt, drifting nebulae and thousands of stars — steering with touch or by tilting your phone. Hidden among the stars are **seven real cosmic objects** to discover.

## The "wow" — you are looking into the past

Every point of light in the night sky left its source at a different moment in time. The Sun you see is 8 minutes old. Betelgeuse might have already exploded and we wouldn't know yet. The light from Andromeda began travelling *before humans existed*.

And here's the part we almost never think about: **right now, light is reflecting off you and racing outward into space** — and one day it will wash over those same stars. Tap the **✦ Light of Now** button and watch a shell of *this exact moment* expand outward, sweeping past each object in true distance order and telling you both when its ancient light left, and the year *your* light of today will finally arrive there.

## Controls

- **Drag** (one finger / mouse) — look around the scene
- **Pinch / scroll** — zoom in and out
- **Tilt your phone** — parallax "lean into it" motion (tap ⟲ to enable; iOS asks permission)
- **Tap a glowing star** — discover a real cosmic object and its light-travel story
- **✦** — replay the Light of Now sweep
- **♪** — ambient soundscape · **⛶** — fullscreen

## Run it locally

Because it uses JavaScript modules, open it through a tiny local web server rather than double-clicking the file:

```bash
cd starwander
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy to GitHub Pages

**Option A — the quick web way (no command line)**

1. Create a new repository on GitHub (e.g. `starwander`).
2. Click **Add file → Upload files**, drag in `index.html` (and `README.md`), and commit.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source: Deploy from a branch**, **Branch: `main`**, folder **`/ (root)`**, and **Save**.
5. Wait ~1 minute — your site will be live at `https://<your-username>.github.io/starwander/`.

**Option B — with git**

```bash
cd starwander
git init
git add index.html README.md
git commit -m "STARWANDER: interactive 3D cosmos"
git branch -M main
git remote add origin https://github.com/<your-username>/starwander.git
git push -u origin main
```

Then enable Pages under **Settings → Pages** as in Option A, step 3–5.

> Tip: if you want it at the root `https://<your-username>.github.io/` instead of a sub-path, name the repository exactly `<your-username>.github.io`.

## Make it yours

Everything lives in the single `index.html` file:

- **The seven objects** — edit the `OBJECTS` array to change the names, distances, and the past/future "light echo" lines (or add more; the counter updates automatically).
- **Colours & mood** — tweak `crystalColors`, the nebula colours in `nebColors`, or the planet bands in `makePlanetTexture()`.
- **Glow** — adjust the `UnrealBloomPass` strength/threshold for more or less bloom.
- **Motion** — `controls.autoRotateSpeed`, tilt sensitivity, and the sweep timing (`echo.dur`) are all near the top of their sections.

## Credits

Built with [Three.js](https://threejs.org) (loaded from the jsDelivr CDN). Distances and light-travel facts are based on widely published astronomical figures and are rounded for readability.
