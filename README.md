# Swanson / Science of Yoga starter extraction for Overload

This zip contains cropped page images from the uploaded PDF, organized into generic LLM-recognizable groups such as `group-quads`, `group-hamstrings`, `group-glutes`, `group-spine`, `group-breathing`, and `group-recovery`.

Use `data/rest_facts_image_manifest.csv` or `.json` to connect images to rest timer facts. The same source page may appear in multiple group folders so the app or an LLM can discover it by muscle group. The canonical non-duplicated copy is in `public/science-yoga-book/_all_pages`.

Suggested app placement:

```txt
public/science-yoga-book/...
src/data/restFactsFromSwansonStarter.ts
```

For Loveable: upload the `data/rest_facts_image_manifest.csv` plus the `public/science-yoga-book` folder. Ask it to replace hardcoded `FACTS` / `EXERCISE_FACTS` with data-driven lookup by `exerciseId`, `category`, and `llm_recognized_group`.
