# Design: "What I Build" Section Redesign

**Date:** 2026-04-23
**Status:** Approved

## Problem

The current "What I Build" section only shows public repositories. Private and in-progress work is
invisible, giving an incomplete picture of active projects.

## Goal

Expand the section to show both published and actively-in-progress work using inline emoji status
indicators, without adding new sections or changing the overall README structure.

## Design Decision

**Approach: Inline status labels**

Each category lists all items (public + coming soon) together in a single line:

- 🟢 = published, public GitHub link
- 🔜 = actively in progress, private — name + short description in italics, no link

Rejected alternatives:
- Split per-category sub-lists (adds visual weight and repetition)
- Standalone "In the Lab" section (separates related work from its category context)

## Items

| Repo | Category | Status |
|------|----------|--------|
| `pytest-playground` | Test Infrastructure | 🟢 published |
| `robotframework_twitch` | Test Infrastructure | 🟢 published |
| `tr-toolkit` | Test Infrastructure | 🔜 coming soon |
| `proj-visual-regression` | Test Infrastructure | 🔜 coming soon |
| `Jenkins-pipelines-playground` | CI/CD & Platform | 🟢 published |
| `ShareLibrary` | CI/CD & Platform | 🟢 published |
| `actions-learning-pathway` | CI/CD & Platform | 🟢 published |
| `jc-toolkit` | CI/CD & Platform | 🔜 coming soon |
| `coinmarketcapAPI` | Python Tooling & CLI | 🟢 published |
| `configuration_loader` | Python Tooling & CLI | 🟢 published |
| `CLI_template` | Python Tooling & CLI | 🟢 published |
| `python-cli-example` | Python Tooling & CLI | 🟢 published |
| `hearsay-note` | Python Tooling & CLI | 🔜 coming soon |
| `programming_arduino` | Edge & Embedded | 🟢 published |
| `Daily-Metal-Prices` | Edge & Embedded | 🟢 published |

## 🔜 Item Descriptions

- `tr-toolkit` — _(TestRail API toolkit)_
- `proj-visual-regression` — _(visual regression testing framework)_
- `jc-toolkit` — _(Jira & Confluence workflow toolkit)_
- `hearsay-note` — _(screenshot-to-Obsidian knowledge capture)_

## Constraints

- README.md only — no other files changed
- Pre-commit hooks must pass (pymarkdown with MD041, MD013, MD036 disabled)
- No new sections added to README structure
