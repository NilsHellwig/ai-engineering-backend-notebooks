# CLAUDE.md

Guidance for working in this repo.

## What this repo is

Jupyter notebooks teaching the **backend/infrastructure side** of AI Engineering — running and operating the systems behind an LLM application (vector databases, serving, storage, ...), as opposed to the application-layer focus of the sister repo [ai-engineering-notebooks](https://github.com/NilsHellwig/ai-engineering-notebooks). Read that repo's `README.md`/`setup.md` for tone and conventions if unsure — this repo mirrors its style closely, just with a backend lens (e.g. reaching for Docker/client-server setups instead of stopping at "just `pip install` and use it").

## Structure conventions

- `chapter/NN_short_name/` — one folder per chapter, two-digit zero-padded prefix, snake_case name (e.g. `chapter/01_chroma/`).
- Single-notebook chapters: `chapter/NN_short_name/NN_intro_topic.ipynb`, filename mirrors the folder.
- Multi-notebook chapters (if a topic needs splitting later): `NN_1_...ipynb`, `NN_2_...ipynb`, etc., meant to be read in that order.
- `chapter/NN_short_name/content/` — any data files, cached artifacts, or supporting `.py` modules a chapter's notebooks need.
- `_ressources_chroma/` is raw reference material (a scrape of Chroma's official docs) to draw on when writing Chroma content — don't edit it, don't copy it verbatim into notebooks; rewrite pedagogically.

## Notebook style

- First cell: `# Notebook: <Title>` (H1), with an emoji if it fits, plus `## 📚 Sources` early on linking the official docs pages the chapter draws from.
- Prose explains **why**, not just what — bold key terms on first use, inline code for identifiers, `>` blockquotes for pull-out definitions.
- Code cells are real and runnable, with teaching-oriented inline comments.
- Sections use `## N. Section Title` numbered headers.
- Exercises: `### Exercise N: <Name>` with a `**Task:**` description, an empty solution cell, then a collapsed solution:
  ```markdown
  <details>
  <summary><b>Show Solution</b></summary>

  ```python
  # solution code
  ```

  </details>
  ```
- No explicit "Summary" footer needed — chapters can just end after the last exercise's solution.

## Tooling

- `uv` manages the environment; dependencies are pinned exactly in `pyproject.toml`, resolved in `uv.lock`. Add new deps with `uv add <package>` rather than hand-editing version pins, and check PyPI for the current latest version when a chapter needs something new.
- This repo is cloned directly (unlike the main course repo, which is not) — `git clone` + `uv sync` is the whole setup.

## When adding a new chapter

1. Create `chapter/NN_short_name/`.
2. Write the notebook following the style above.
3. Add any new deps to `pyproject.toml` via `uv add`.
4. Add a `### **NN - Title**` entry to the "Course Contents" section of `README.md`, matching the format of existing entries.
