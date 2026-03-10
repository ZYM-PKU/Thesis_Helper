---
name: "Thesis Bibliography Rules"
description: "Use when updating Source/main.bib, normalizing BibTeX entries, fixing citation metadata, standardizing English title capitalization, or syncing references from published conference papers in Projects."
applyTo: "Source/main.bib"
---
# Thesis Bibliography Rules

- Treat Source/main.bib as the single bibliography source for the thesis.
- When the same paper appears in multiple places, prefer the latest formally published conference or journal version over drafts, rebuttals, supplements, or arXiv preprints.
- Normalize the whole file consistently when editing it; do not leave mixed styles across old and new entries.
- Check each bibliography entry one by one and keep every English title in a unified title-case format, with the first letter of each major word capitalized unless BibTeX protection braces are needed for acronyms, model names, or special tokens.
- Preserve author order from the published source.
- Update venue names, page ranges, year, publisher or organization, and other metadata to match the published paper.
- Avoid duplicate entries that refer to the same published work under different keys unless the thesis truly needs separate citations.
- If an arXiv entry has no formal publication yet, keep it as arXiv but still normalize its field formatting to match the rest of the bibliography.
- Preserve citation keys already used in the thesis unless there is a strong reason to rename them; if a key must change, update all in-text citations accordingly.
- Before finishing, check for malformed BibTeX syntax, inconsistent field casing, missing commas, and obvious metadata conflicts.