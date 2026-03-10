---
name: "Import Paper Figures"
description: "Import figures from Projects into the thesis, copy them into Source/img with normalized names, and insert them into the appropriate Source chapter sections."
argument-hint: "Which chapter, paper project, or figure set should be imported?"
agent: "Thesis Writer"
---
Import published-paper figures into the thesis manuscript.

Requirements:
- Work inside this workspace only.
- Treat Source as the thesis manuscript and Projects as source material.
- Identify the most relevant figures from the specified paper project or chapter context.
- Copy selected figures into Source/img using clear project-prefixed names.
- Avoid duplicate or redundant figure imports when an equivalent figure already exists in Source/img.
- Insert or update the LaTeX figure environment in the most appropriate Source chapter file.
- Write academically appropriate Chinese captions that match the surrounding narrative.
- Keep figure labels consistent, descriptive, and stable for later cross-references.
- If a figure requires discussion text to make sense in context, add the necessary transitional paragraph around the figure.

Output:
- List which source figures were selected.
- List the new or reused filenames under Source/img.
- List which thesis chapter file was updated.
- Mention any figures that were rejected and why.