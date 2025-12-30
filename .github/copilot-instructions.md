## Purpose
This file helps AI coding agents become productive quickly in this repository.

## Quick summary
- Primary project artifact: `Numerology.ipynb` (Jupyter notebook).  
- Minimal repository: no `src/` directory, no `requirements.txt`, no tests present.  
- `README.md` contains only a short title; most project logic and intent live in the notebook.

## Top-level guidance for edits
- Prefer notebook-first edits: update code cells and keep explanatory markdown cells intact.  
- When extracting reusable code, place modules under a new `src/` folder (create `src/__init__.py`). Example: move helper functions into `src/analysis.py` and import them from the notebook with `from src.analysis import ...`.
- Check the first code cells of `Numerology.ipynb` for import statements to discover dependencies before running.

## Running & verifying changes
- No automation is provided. Use a Jupyter server or VS Code Notebook to run `Numerology.ipynb`.  
- To verify edits locally: open `Numerology.ipynb` and run affected cells (use incremental runs).  
- If you introduce external packages, add a `requirements.txt` at repo root and document the install command in `README.md`.

## Repository conventions discovered
- Notebook outputs are not globally ignored; `.gitignore` contains `.ipynb_checkpoints` only. Expect notebook outputs to be present in commits unless you clear them or add a filter.  
- Keep commits small and focused when changing the notebook (one logical change per commit) to make review easier.

## When creating new files
- If adding Python modules or scripts, prefer `src/` or `scripts/` at repo root.  
- Update `README.md` to summarize any new runnable components and provide run commands.

## What not to assume
- There is no CI, test harness, or dependency manifest in this repository. Do not assume tests or build scripts exist.

## Useful examples to include in PRs
- Show the notebook cell diff and a short note describing which cells to re-run.  
- If extracting code to `src/`, include a tiny usage snippet in `Numerology.ipynb` showing the import and one example call.

## Where to look first
- `Numerology.ipynb` — primary content and logic.  
- `README.md` — currently minimal; update when you add runnable components.  
- `.gitignore` — confirms only `.ipynb_checkpoints` is ignored for notebooks.

## Requirements placeholder & how to generate
- Add a `requirements.txt` at repo root when external packages are needed.
- Quick ways to produce an accurate list:
  1. Convert notebook to script then use pipreqs:
     - jupyter nbconvert --to script Numerology.ipynb
     - pipreqs . --force --ignore .ipynb_checkpoints
  2. If you run the notebook in a venv, export the environment:
     - pip freeze > requirements.txt
  3. Quick manual extraction: open the first code cells of `Numerology.ipynb` and collect `import` lines.
- Example placeholder (see repo root `requirements.txt`) — verify against the notebook imports before publishing.

If anything above is unclear or you want the file to emphasize additional workflows (for example: adding `requirements.txt` automatically, a preferred test runner, or a CI recipe), tell me which workflows to add and I will update this file.