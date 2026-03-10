# Thesis Helper

<div align="center">

**A GitHub Copilot + MCP workflow for turning research projects into a coherent Chinese degree thesis**

✨ From papers and project assets to a thesis-ready LaTeX manuscript

<p>
  <img src="https://img.shields.io/badge/VS%20Code-Copilot%20Customizations-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white" alt="VS Code Copilot Customizations" />
  <img src="https://img.shields.io/badge/MCP-Ready-111111?style=for-the-badge" alt="MCP Ready" />
  <img src="https://img.shields.io/badge/LaTeX-Thesis%20Workflow-008080?style=for-the-badge&logo=latex&logoColor=white" alt="LaTeX Thesis Workflow" />
  <img src="https://img.shields.io/badge/Language-Chinese%20Academic%20Writing-B31B1B?style=for-the-badge" alt="Chinese Academic Writing" />
</p>

</div>

---

## 🎯 Why This Repo Exists

> [!NOTE]
> ### 献给所有苦于毕业论文写作的研究生们：
> 在 AI 高速发展的当下，我们理应有一种途径让自己能够解放双手，在 2h 内完成一篇内容结构完整，高度可用的毕业论文，而这个 repo 将帮你实现这一点。不过，请你注意：
> - 本 repo 适用于有一定 LaTeX 基础，且打算完全基于 LaTeX 写作论文的研究生。
> - 你最好已经完成开题报告，这样本 repo 可以帮你从一个良好底座上逐步垒砌起论文的高墙。
> - 建议使用 Git 进行论文版本管理，方便回溯。

## ✨ Repo Features

This repo provides two complementary custom agents for different stages of thesis work:

- `Thesis Writer`: expand, rewrite, synchronize, and build the thesis manuscript from `Projects/` into `Source/`
- `Thesis Reviewer`: review a nearly completed thesis from both LaTeX source and compiled PDF, then apply conservative fixes and verification passes

Together, they cover both the drafting workflow and the late-stage review workflow, so the repo can support thesis production from initial expansion to final polishing.

## 🧰 Prerequisites

<details>
<summary><strong>Install Requirements</strong></summary>


You need the following before this repo becomes fully useful:

1. Latest VS Code with GitHub Copilot Chat enabled.
2. Node.js for `npx`-based MCP servers.
3. `uv` for `uvx`-based MCP servers.
4. A LaTeX toolchain with `latexmk` as the default build entry if you want build validation.

Recommended local tools:

```bash
# macOS
brew install node
brew install --cask mactex-no-gui
curl -LsSf https://astral.sh/uv/install.sh | sh
```

For LaTeX, this repo assumes `latexmk` is your default compiler driver. The simplest installation options are:

- macOS: install `MacTeX` or `mactex-no-gui`, which includes `latexmk`, `xelatex`, and `biber`
- TeX Live users: make sure the `latexmk` package is installed alongside your XeLaTeX and bibliography tools
- Verify the setup with `latexmk -v`

</details>

<details>
<summary><strong>Setup MCP Servers</strong></summary>

This repo is designed to work well without MCP, but the full workflow is much better with it.

#### MCP Servers Used By The Thesis Agent

| MCP Server | Why It Matters | Required |
| --- | --- | --- |
| `microsoft/markitdown` | Convert PDFs into Markdown so the agent can inspect papers, supplements, or reference theses more effectively | Recommended |
| `io.github.h-lu/crossref-cite-mcp` | Resolve citation metadata and fetch authoritative publication details | Recommended |
| `io.github.hy20191108/semantic-scholar-mcp` | Explore papers, citations, author metadata, and scholarly context | Recommended |
| `io.github.imnotdev25/paper-mcp` | Fetch paper metadata, full text, PDF links, citations, and references | Recommended |
| `io.github.tavily-ai/tavily-mcp` | Crawl or extract web content when source material lives online | Optional |


#### Add MCP Servers to Your VS Code

1. Add the contents in `mcp_add_ons.json` to your MCP Config

  On macOS, the user-level MCP config is typically:

  ```text
  ~/Library/Application Support/Code/User/mcp.json
  ```

  If your VS Code setup exposes an MCP settings UI, you can edit it there instead.

2. Reload your VS Code

</details>


<details>
<summary><strong>Prepare Your Files</strong></summary>

1. Clone this repo

2. Put the source files of your thesis （可以是你的开题报告） in `Source` and keep the folder structure:

  - keep the main thesis entry file and bibliography at the top level of `Source`, for example `main.tex` and `main.bib`
  - keep chapter files under `Source/chap/`
  - keep thesis figures under `Source/img/`

3. Put all your previous projects (source files) in `Projects` (similar to 2)

4. (Optional) Put any reference thesis (pdfs) in `Refs`

</details>


## 🚀 Start Running!

### Write the Paper

Select the `Thesis Writer` custom agent in your Copilot, select your favourite LLM, and then enter this prompt:

```text
开始运行
```

and, ... Boom!

### Review the Paper

Select the `Thesis Reviewer` custom agent in your Copilot, select your favourite LLM, and then enter this prompt:

```text
开始评审
```

<details>
<summary><strong>（Optional）Prompt Commands</strong></summary>

These prompts are useful when you do not want the full pipeline.

#### 1. Expand A Paper Into A Thesis Section

```text
/Expand Paper Into Thesis Section
```

Suggested input:

```text
Expand Source/chap/3_method.tex from Projects/MyPublishedPaper, focusing on method details and experiment analysis.
```

#### 2. Import Figures From A Paper Project

```text
/Import Paper Figures
```

Suggested input:

```text
Import the most relevant overview, pipeline, and qualitative comparison figures from Projects/MyPublishedPaper into the corresponding Source chapter.
```

#### 3. Normalize The Thesis Bibliography

```text
/Normalize Thesis Bibliography
```

Suggested input:

```text
Run full bibliography normalization and prioritize formally published venue metadata.
```

</details>

## 🛠️ Troubleshooting

<details>
<summary><strong>MCP servers do not show up in VS Code</strong></summary>

Check these first:

- `node`, `npx`, `uv`, and `uvx` must be available in your shell path.
- Your `mcp.json` must be valid JSON.
- API-backed servers need the required keys or emails.
- Reload the VS Code window after changing MCP configuration.

</details>

<details>
<summary><strong>The agent cannot find papers or metadata</strong></summary>

Possible causes:

- the relevant MCP servers are not configured
- the project folder under `Projects/` does not contain the expected artifacts
- the repo uses different file paths than the packaged prompts and instructions assume

</details>

<details>
<summary><strong>Build validation fails</strong></summary>

Check whether your environment provides:

- `latexmk`
- `xelatex`
- `biber`

Also verify that figure paths, chapter includes, and bibliography file paths match your actual thesis project.

</details>