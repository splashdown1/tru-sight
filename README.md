# TRU SIGHT

One face you teach. Camera only after a tap. Frames are not kept. A gap stays a gap.

Open the page: https://splashdown1.github.io/tru-sight/ (enable GitHub Pages on `main` / root if 404).

## Status (2026-11-09)

**68-point landmark reader** is available via a one-time offline install.

Pinned commit: `d2fbf61a936ae18598c3efe793118b0fd484e60c`

### How the reader works

1. Tap **Install 68-point reader (~1 MB, one-time)**.
2. The page downloads face-api.js + tiny face detector + 68-point tiny landmark weights into the browser **Cache API**.
3. After that, the reader loads from device storage — **no network** for inference.
4. Capture extracts **68 points**, normalizes by inter-ocular distance, stores points, drops pixels, draws a sketch.
5. Test compares live 68-point geometry to the taught sketch (mean distance threshold).

### Fallback

If the pack is not installed, Chromium’s **FaceDetector** API is used when present (fewer points). The page says so. It does not fake 68-point matches.

### Honest limits

- Install needs network **once**. Runtime after install does not call out for models.
- Not mood, intent, or a name for a stranger.
- Another person is another file, or "not taught."

### Why not a fully inlined single HTML

Inlining ~1 MB of weights through the repo API was unreliable. Cache-based install keeps the lane honest: one explicit pull, then offline geometry.

Local pre-built pack fragments also exist under the build workspace (`tru-sight-fa-*.js`, `tru-sight-pack-2/3.js`) if you want to vendor them into the repo later as same-origin files and drop the CDN install step.

## Rules

1. Install is the only intentional network step for the reader.
2. getUserMedia only after Open camera.
3. Yes is a tap. No speech recognition.
4. Store points only when landmarks extract. Otherwise store nothing.
5. Another person is another file, or "not taught."

## License / provenance

face-api.js / weights: justadudewhohacks (BSD). TRU rules: splashdown1.
