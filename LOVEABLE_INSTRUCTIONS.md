# Overload Knowledge Base v3 — exact repo paths

Use this file set at the root of the GitHub Pages repo. Entry point:

`https://dawnai-ethicist.github.io/overload-knowledge-base/knowledge-index.json`

## Critical fix

Do not use stale paths such as `group-full-body/...`. They do not exist. This v3 metadata was generated from the exact repository zip, so `images.json` points only to real files.

## Runtime logic

1. Fetch `knowledge-index.json` once.
2. Fetch `exercise-map.json`, `concepts.json`, `images.json`, `rest-facts.json`, and `yoga-pose-map.json`.
3. On rest timer start, use current `exerciseId`.
4. Look up primary and secondary concept IDs from `exercise-map.json`.
5. Select rest facts whose `conceptIds` overlap with those concepts.
6. Select image URLs from `images.json` using each fact's `imageIds`.
7. Prefer `image.url`; if an image fails, try `candidateUrls`.
8. Optionally show a complementary yoga pose from `yoga-pose-map.json`.
9. If anything fails, keep the timer running and fall back to existing cards.

## UI card

Show: title, concise body, one image, optional pose recommendation, and a next/refresh card button.
