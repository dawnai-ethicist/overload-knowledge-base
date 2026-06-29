# Overload Knowledge Base v2: Loveable Instructions

Use this repository as a static anatomy knowledge base for the rest timer.

Entry point:

```txt
https://dawnai-ethicist.github.io/overload-knowledge-base/knowledge-index.json
```

## Required behavior

1. Fetch `knowledge-index.json`.
2. Then fetch `exercise-map.json`, `concepts.json`, `images.json`, and `rest-facts.json`.
3. When a rest timer starts, read the current `exerciseId`, `exerciseName`, and/or category.
4. Match the exercise to `exercise-map.json` by exact key first, then by `searchTerms`.
5. Use the matched primary and secondary concept ids to choose relevant facts from `rest-facts.json`.
6. Show one anatomy card during the rest timer with:
   - title
   - body
   - image
   - optional source page
7. Use `images.json` to resolve image URLs. Try `url` first, then any `candidateUrls` if the image fails.
8. Cache the JSON in local state/session storage so the app does not refetch constantly.
9. Avoid repeating the same fact during the same workout.

## Important

Do not move the image folders. These JSON files teach the app how to use the folders already in the repo root.

## Suggested fallback

If no exercise match is found, use concepts:

- `breathing`
- `cardio_recovery`
- `nervous_motor`
- `skeletal_joints`

These work for generic rest periods.
