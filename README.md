# TRU SIGHT

One file. One face you teach. Camera only after a tap. Frames are not kept. A gap stays a gap.

Open the page: https://splashdown1.github.io/tru-sight/

## Status (2026-11-09)

Skeleton is built (`index.html`).

- Camera flow, speechSynthesis labels, IndexedDB store, capture/test UI, and the honest label set are in place.
- **Landmark reader is not packed.** Capture records intent and keeps the store structure. It does not extract points, draw a sketch, or invent a match. The page says so.
- Shelf still does not promote it as a finished lane. A face does not make Lifeline or the field cards smarter.

## What this is

One person, one file. The file may learn the poses that person taught, and no one else's. Sharing is handing the file over. If it is not handed over, it is not shared.

## What it is not

- Not a mood reader.
- Not an intent guesser.
- Not a name for a stranger.
- Not a cloud.
- Not the answer to four weeks without power.

## Rules already set

1. One HTML file. No network after the page is on the phone. If it has to call out to run, it is not a lane.
2. The camera may preview. Frames are not written.
3. A write happens only in this order: TRU speaks a label, the person poses, the person says capture. No prompt, no capture. Prompt without a yes, no capture.
4. What is kept is points and a sketch. The pixels are dropped in that same moment. localStorage is the wrong box. IndexedDB holds the sketches.
5. A later look may say "this is the smile you taught" or "not taught." It may not invent cry, confused, or a name.
6. Spoken prompts use speechSynthesis. Spoken yes does not. Browser speech recognition leaves the phone. The yes is a tap.
7. A match needs a reader packed in the file. No reader, the card says not packed. A pixel diff is not a face.
8. Opening the file from the phone may refuse the camera. The page has to be served from the phone itself, or the shutter never comes on.
9. Honest set, no more: face here, no face, eyes open, eyes shut, smile, grin, mouth open, brow up, brow down, look left, look right, look down, and cry only if the mouth and brow were taught together. Past that, not packed.
10. Another person is another file, or "not taught." This ship does not know the fleet.

## Next real step

Pack a true landmark reader inside the single file (no network fetch). Until that lands, geometry stays a gap. Do not widen the prompt. Do not fake matches.

## License / provenance

Source-bound rules. Owner: splashdown1.
