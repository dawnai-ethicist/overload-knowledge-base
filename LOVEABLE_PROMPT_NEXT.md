# Prompt for Loveable: Overload Knowledge Graph Integration

Use the GitHub Pages knowledge base entry point:

https://dawnai-ethicist.github.io/overload-knowledge-base/knowledge-index.json

Integrate the rest timer with the new files:

- exercise-map.json
- ontology.json
- book-index.json
- images.json
- image-context.json
- yoga-pose-map.json
- rest-learning-paths.json

Requirements:

1. When the workout/session loads, fetch knowledge-index.json once and cache the referenced JSON files for the session.
2. During the rest timer, identify the current exerciseId or exerciseName.
3. Normalize the exercise id/name to lowercase kebab-case and match it to exercise-map.json. Also check aliases.
4. Use exercise-map.json to retrieve ontologyTopics, bookTopics, preferred imageIds, and recommendedYogaGoals.
5. Use rest-learning-paths.json to decide which kind of card to show next: anatomy, biomechanics, yoga-pose, or body-system.
6. Use image-context.json to choose and explain an image. Do not show an image if its URL fails; try the next imageId.
7. Use yoga-pose-map.json to suggest only gentle rest-timer-safe poses. Do not suggest intense end-range stretching before heavy sets.
8. Track shown cards in local state/localStorage so the same fact or pose does not repeat until the available cards are exhausted.
9. Never block or break the timer if GitHub files fail to load. Fall back to the current built-in RestTimer facts.
10. Display the rest card beneath the timer with: title, image, 1–3 sentence explanation, and optional gentle pose suggestion.

Important: do not make the LLM read the full PDF at runtime. The app should use the JSON files as retrieval metadata.
