# What I Build Section Update — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Update the "What I Build" section in README.md to show both published (🟢) and actively in-progress (🔜) projects inline within each category.

**Architecture:** Single-file README change. Each category paragraph gets 🟢 prefixes on public repo links and 🔜 entries (name + italic description, no link) for private/coming-soon work.

**Tech Stack:** Markdown, pre-commit (pymarkdown linter)

---

### Task 1: Update "What I Build" section in README.md

**Files:**
- Modify: `README.md:11-35`

**Step 1: Replace the existing "What I Build" section**

Open `README.md` and replace lines 11–35 with:

```markdown
## What I Build

**Test Infrastructure & Frameworks**
Selenium grids on Kubernetes, containerized test environments, mobile testing platforms,
and Python-based automation frameworks —
🟢 [`pytest-playground`](https://github.com/CubeVic/pytest-playground) ·
🟢 [`robotframework_twitch`](https://github.com/CubeVic/robotframework_twitch) ·
🔜 `tr-toolkit` _(TestRail API toolkit)_ ·
🔜 `proj-visual-regression` _(visual regression testing framework)_

**CI/CD & Platform Tooling**
Jenkins pipelines, GitHub Actions, shared libraries, and developer productivity tools —
🟢 [`Jenkins-pipilines-playground`](https://github.com/CubeVic/Jenkins-pipilines-playground) ·
🟢 [`ShareLibrary`](https://github.com/CubeVic/ShareLibrary) ·
🟢 [`actions-learning-pathway`](https://github.com/CubeVic/actions-learning-pathway) ·
🔜 `jc-toolkit` _(Jira & Confluence workflow toolkit)_

**Python Tooling & CLI**
Reusable packages, configuration management, and CLI scaffolding —
🟢 [`coinmarketcapAPI`](https://github.com/CubeVic/coinmarketcapAPI) ·
🟢 [`configuration_loader`](https://github.com/CubeVic/configuration_loader) ·
🟢 [`CLI_template`](https://github.com/CubeVic/CLI_template) ·
🟢 [`python-cli-example`](https://github.com/CubeVic/python-cli-example) ·
🔜 `hearsay-note` _(screenshot-to-Obsidian knowledge capture)_

**Edge & Embedded**
Raspberry Pi deployments, hardware-integrated solutions, Arduino experiments —
🟢 [`programming_arduino`](https://github.com/CubeVic/programming_arduino) ·
🟢 [`Daily-Metal-Prices`](https://github.com/CubeVic/Daily-Metal-Prices)
```

**Step 2: Run pre-commit to validate**

```bash
pre-commit run --files README.md
```

Expected: All hooks pass. If pymarkdown reports an error, check the disabled rules in `.pre-commit-config.yaml` (MD041, MD013, MD036 are already disabled).

**Step 3: Review the diff**

```bash
git diff README.md
```

Verify the 🟢/🔜 entries appear correctly in each category.

**Step 4: Stage for commit (user commits)**

```bash
git add README.md docs/plans/2026-04-23-what-i-build-redesign.md docs/plans/2026-04-23-what-i-build-update.md
```

Then provide this suggested commit message to the user:

```
feat: add coming soon projects to What I Build section

Add inline 🟢/🔜 status indicators to show both published and
actively in-progress private projects within each category.
```

> **Note:** Do NOT run `git commit` — the user commits themselves per project policy.
