# What I Build v2 — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Replace the "What I Build" section in README.md with a clean, prose-free layout: bold category heading, linked repos on one line, in-progress work as a subtle italic line below.

**Architecture:** Single-file README change. Replace lines 11–40 (the entire "What I Build" block including the trailing `---` separator). No emoji status indicators. No category descriptions.

**Tech Stack:** Markdown, pre-commit (pymarkdown linter)

---

### Task 1: Replace the "What I Build" section in README.md

**Files:**
- Modify: `README.md:11-40`

**Step 1: Open README.md and replace the current "What I Build" block**

Find the block starting at `## What I Build` (line 11) through the closing `---` (line 41) and replace it with:

```markdown
## What I Build

**Test Infrastructure & Frameworks**
[`pytest-playground`](https://github.com/CubeVic/pytest-playground) · [`robotframework_twitch`](https://github.com/CubeVic/robotframework_twitch)
*(tr-toolkit · proj-visual-regression — in progress)*

**CI/CD & Platform Tooling**
[`Jenkins-pipilines-playground`](https://github.com/CubeVic/Jenkins-pipilines-playground) · [`ShareLibrary`](https://github.com/CubeVic/ShareLibrary) · [`actions-learning-pathway`](https://github.com/CubeVic/actions-learning-pathway)
*(jc-toolkit — in progress)*

**Python Tooling & CLI**
[`coinmarketcapAPI`](https://github.com/CubeVic/coinmarketcapAPI) · [`configuration_loader`](https://github.com/CubeVic/configuration_loader) · [`CLI_template`](https://github.com/CubeVic/CLI_template) · [`python-cli-example`](https://github.com/CubeVic/python-cli-example)
*(hearsay-note — in progress)*

**Edge & Embedded**
[`programming_arduino`](https://github.com/CubeVic/programming_arduino) · [`Daily-Metal-Prices`](https://github.com/CubeVic/Daily-Metal-Prices)

---
```

**Step 2: Run pre-commit to validate**

```bash
pre-commit run --files README.md
```

Expected: All hooks pass. If pymarkdown reports an error, check `.pre-commit-config.yaml` — MD041, MD013, MD036 are already disabled. The italic lines use `*( ... )*` syntax which is valid inline emphasis.

**Step 3: Review the diff**

```bash
git diff README.md
```

Verify:
- No prose descriptions under category headings
- Published repos are linked with backtick names and `·` separators
- In-progress lines are italic and have no links
- Edge & Embedded has no in-progress line

**Step 4: Stage files (user commits)**

```bash
git add README.md docs/plans/2026-04-23-what-i-build-v2-design.md docs/plans/2026-04-23-what-i-build-v2-update.md
```

Suggested commit message for the user:

```
refactor: simplify What I Build section layout

Replace prose descriptions and emoji indicators with clean category
headings, linked repos, and subtle italic in-progress lines.
```

> **Note:** Do NOT run `git commit` — the user commits themselves per project policy.
