# TRU SIGHT

One face you teach. Camera only after a tap. Frames are not kept. A gap stays a gap.

Open the page: https://splashdown1.github.io/tru-sight/ (enable GitHub Pages on `main` / root if 404).

## Status (2026-11-09)

Landmark reader is **packed** via the browser **FaceDetector** API.

Pinned commit:

`a511a45b5de9ff86164bf544c06a8aa44d5f4304`

### What works

- Camera only after Open camera tap
- Labels via `speechSynthesis`
- Capture reads **one frame**, extracts landmark points, draws a sketch, **drops pixels**, stores normalized points in IndexedDB
- Test extracts live points and compares mean distance (inter-ocular normalized) to the taught sketch
- Match → `this is the {label} you taught`
- No match / no face → `not taught`
- No external network, no CDN, no uploaded model weights

### Honest limits

- FaceDetector is **Chromium**-family (Chrome, Edge, many Chromebooks). Firefox/Safari often lack it → page says the gap.
- Landmark set is the browser’s (typically eyes, nose, mouth) — **not** a full 68-point mesh.
- This is geometry you taught, not mood, intent, or a name for a stranger.

### Optional upgrade path

A full 68-point face-api / MediaPipe pack (~1 MB of weights) can still be dropped in later as same-origin files. Until then, FaceDetector is the packed reader.

## Rules

1. No network required for the reader after the page is on the device.
2. getUserMedia only after the Open camera tap.
3. Yes is a tap. No speech recognition.
4. Store points/sketch only when landmarks are extracted. Otherwise store nothing.
5. Another person is another file, or "not taught."

## License / provenance

Source-bound rules. Owner: splashdown1.
