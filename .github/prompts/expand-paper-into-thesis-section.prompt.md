---
name: "Expand Paper Into Thesis Section"
description: "Rewrite published English paper material into a Chinese thesis section, expanding technical detail while preserving the thesis chapter structure in Source."
argument-hint: "Which thesis chapter or section should be expanded from which paper project?"
agent: "Thesis Writer"
---
Expand a thesis chapter or section from published paper material.

Requirements:
- Work inside this workspace only.
- Treat Source as the thesis manuscript and Projects as source material.
- Identify the exact target chapter or section in Source before writing.
- Use the formally published conference version as the primary source when multiple versions exist.
- Rewrite in formal Chinese academic style suitable for a degree thesis, rather than directly translating paragraph by paragraph.
- Expand technical motivation, method details, experiment design, result analysis, and transitions where the thesis draft is too thin.
- Preserve the surrounding chapter logic, notation, terminology, and LaTeX structure already used in Source.
- If needed, identify figures or tables that should be imported from Projects and place them into Source/img with normalized names.
- If the expanded section changes the thesis-level contribution narrative, note that the abstract, introduction, related work, and conclusion should be synchronized.
- Keep claims, numbers, and citations consistent with the published paper and the thesis draft.

Suggested inputs to resolve:
- target thesis file or section
- source paper project under Projects
- whether the focus is method, experiments, dataset, or discussion

Output:
- State which Source chapter or section was expanded.
- State which paper materials were used.
- Summarize the main additions made beyond the previous thesis draft.
- Mention any figures, tables, or bibliography updates required.
- Mention whether supporting chapters should also be synchronized.