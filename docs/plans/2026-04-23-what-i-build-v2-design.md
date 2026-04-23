# Design: "What I Build" Section v2

**Date:** 2026-04-23
**Status:** Approved

## Problem

The previous design (inline 🟢/🔜 emoji indicators within paragraph descriptions) was visually noisy
and hard to scan. Category descriptions restated what the bold heading already implied.

## Goal

Quick-scan view of breadth — visitor gets a fast overview where categories matter more than
individual repos. Published repos lead; in-progress private work appears subtly below each category.

## Design

**Structure per category:**

```
**Category Name**
[`repo`](link) · [`repo`](link)
*(in-progress-name — in progress)*
```

- Bold heading only — no prose description
- Published repos: linked, backtick names, `·` separator on one line
- In-progress: italic line directly below, `— in progress` label, no link
- In-progress line omitted entirely when a category has no active private work

## Full Section Content

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
```

## Constraints

- `README.md` only — no other files changed
- Pre-commit hooks must pass (pymarkdown with MD041, MD013, MD036 disabled)
- No new sections added to README structure
- Replace lines 11–40 of current README (the entire "What I Build" block)
