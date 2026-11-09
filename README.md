# TRU SIGHT

One face you teach. Camera only after a tap. Frames are not kept. A gap stays a gap.

Open the page: https://splashdown1.github.io/tru-sight/

**GitHub Pages:** Settings → Pages → Deploy from branch **main** / **/** (root). Until that is on, the URL 404s; open `index.html` via a local server instead.

## Status (2026-11-09)

Pinned tip: `20d52377a7205dd2538d5f8afec668ef98f944bd`

### Reader

- **Download model** — one-time ~1 MB pull into Cache API (face-api tiny detector + 68-point landmarks). Then offline.
- **Face detection confidence** slider (0.10–0.90, default 0.40), with show/hide toggle. Stored in `localStorage`.
- Capture stores normalized 68 points; pixels dropped; sketch overlay.
- Test compares geometry; match or `not taught`.
- Fallback: Chromium `FaceDetector` if the pack is not installed (fewer points; labeled honestly).

### Device checklist

1. Enable Pages (or `python3 -m http.server` in the repo folder).
2. Download model → status says ready.
3. Open camera (after tap only).
4. Pick a label → pose → Capture → taught list updates.
5. Same label → Test → match or `not taught`.
6. Bad pose / no face → nothing stored / `not taught`.

### Shelf pin

```bash
python3 tru_shelf.py propose \
  --repo splashdown1/tru-sight \
  --sha 20d52377a7205dd2538d5f8afec668ef98f944bd \
  --path index.html \
  --note "68-point Sight: download model, confidence threshold, offline cache" \
  --by splashdown1
# then: python3 tru_shelf.py approve <id>
# then: python3 tru_shelf.py check
```

Also pin define-modules (Strong's repair) if not already:

```bash
python3 tru_shelf.py propose \
  --repo splashdown1/tru-define-modules \
  --sha 8f511cbf6af6e469142ea3af418512e4fb24ea66 \
  --path TRU-bible-only-v2.1.3.html \
  --note "Strong's repair; define Graces -> G5485" \
  --by splashdown1
```

## Rules

1. Download model is the only intentional network step for the reader.
2. getUserMedia only after Open camera.
3. Yes is a tap. No speech recognition.
4. Store points only when landmarks extract. Otherwise store nothing.
5. Another person is another file, or "not taught."

## License / provenance

face-api.js / weights: justadudewhohacks (BSD). TRU rules: splashdown1.
