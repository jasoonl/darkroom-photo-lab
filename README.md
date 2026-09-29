# Darkroom Photo Lab

A retro photo lab that runs entirely in the browser: camera-brand and film looks (Fujifilm and Sony first), a Lightroom-style developer, frames, date stamps and full-resolution export. Photos never leave the device.

- `/` is the app. `/lab` is the test bench: it loads openly licensed photos from Wikimedia Commons and runs every look on them (clipping, skin-tone and neutral-shift checks plus contact sheets).
- Deployed on Vercel from this repo. Every push to `main` redeploys production.

## Files

| File | What it is |
|---|---|
| `index.html` | The app, in the Claude Design component format (`<x-dc>` template + `DCLogic` class). Also lives as `Main.dc.html` on the Claude Design canvas "Darkroom Photo Lab". |
| `support.js` | The Claude Design component runtime (bundles React 18, MIT) that renders `index.html`. It is third-party code and is not covered by this repo's MIT license. |
| `darkroom-engine.js` | WebGL2 develop pipeline, crop geometry, frames, date stamps, EXIF and RAW-preview reading, tiled export, ZIP. `window.Darkroom`. |
| `darkroom-looks.js` | The look library (110 looks): `p` = colour science, `fx` = effect sliders the look sets. |
| `lab.html` | Test bench. `?per=N` sets photos per source (default 4). |

## Resuming work in a new chat

Paste this: "Darkroom repo is jasoonl/darkroom-photo-lab (Vercel project darkroom-photo-lab). Read README.md, then …". Looks are tuned in `darkroom-looks.js`; the canvas copy (`Main.dc.html`) and `index.html` differ only by the head meta and favicon lines.

## Camera matching (next step)

True calibration needs pairs of the same frame: the camera JPEG in Provia/Standard (or Sony ST) and the same RAW re-rendered in camera with the target film simulation or Creative Look. Fujifilm and Sony bodies both offer in-camera RAW conversion, so one RAW gives every pair.

## License

MIT for this project's own files (`LICENSE`). `support.js` is third-party: see `THIRD_PARTY_NOTICES.md`. A dependency-free version lives at https://github.com/jasoonl/darkroom-photo-lab-html-java.
