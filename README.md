# Animated Cat AR — test demo

A second, standalone AR demo used to test an animated (rigged) character.
Independent of the original AR-Demo; it uses its own marker and its own model.

## Publish

Upload every file in this folder to the root of the repository, then enable
**Settings → Pages → Deploy from a branch → main → /(root)**.

## Test

1. Print `card2-print-a4.svg` at 100% scale on matte paper.
2. Open the Pages URL on your phone and tap **Start AR camera**.
3. Point at the black square. The cat appears and starts walking.
4. Tap the animation chip (top right) to cycle through all seven clips.

## What is different from the first demo

- `Cat-Animation.glb` is rigged: 24 joints, 7 animation clips, 6,261 triangles.
  Playback is driven by `THREE.AnimationMixer` from the `marker-status`
  component's tick, because A-Frame ships no `animation-mixer` component.
- The model is auto-fitted to the marker at load, so its export scale does not
  need to match anything.
- `card2.patt` is a different pattern from the original demo's marker, chosen so
  the two cannot be confused (correlation 0.26) and so the pattern is not
  rotationally ambiguous (self-correlation 0.07).

## Redeploying

Bump `CACHE_VERSION` in `sw.js` whenever you change `ar.html`, `index.html` or
the model, or the service worker will keep serving the cached copies.
