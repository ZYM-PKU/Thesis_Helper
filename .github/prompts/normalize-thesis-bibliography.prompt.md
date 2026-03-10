---
name: "Normalize Thesis Bibliography"
description: "Fully clean and normalize Source/main.bib using published paper metadata from Projects and consistent BibTeX formatting across the whole thesis bibliography."
argument-hint: "Run full bibliography normalization, or specify special cases to prioritize"
agent: "Thesis Writer"
---
Normalize the thesis bibliography end to end.

Requirements:
- Operate on Source/main.bib as the single bibliography source for the thesis.
- Perform full-file normalization, not partial cleanup.
- Compare entries against the published paper metadata available in Projects and prefer formally published conference or journal versions over drafts, rebuttals, supplements, or preprints when conflicts exist.
- Keep English titles in consistent title case across the whole file, with braces only where needed to protect acronyms, model names, or special tokens.
- Preserve existing citation keys when possible; if a key truly must change, update all affected thesis citations as part of the same task.
- Remove or merge obvious duplicates that refer to the same published work.
- Normalize venue names, page ranges, year, organization or publisher fields, and author ordering.
- Retain arXiv entries only when no formal publication exists, but still normalize their formatting.
- Check the final file for malformed BibTeX syntax or metadata conflicts.

Output:
- Summarize how many entries were normalized, added, merged, or removed.
- List the entries whose publication metadata changed materially.
- Mention any citation keys that were preserved or renamed.
- Mention any unresolved bibliography ambiguities that still need confirmation.